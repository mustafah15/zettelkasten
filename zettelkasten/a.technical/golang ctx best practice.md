---
tags:
  - goLang
type: permanent
parent: "[[why context propgation is important from golang point of view]]"
---
#### **1. Context as First Parameter**

Always pass context as the first parameter to functions, with the conventional name `ctx`:


```go
// ✅ Good
func GetUser(ctx context.Context, userID string) (*User, error)

// ❌ Bad
func GetUser(userID string, ctx context.Context) (*User, error)
func GetUser(c context.Context, userID string) (*User, error)  // wrong name
```

#### **2. Never Store Context in Structs**

Context should flow through your program via function parameters, not be stored:



```go
// ❌ Bad - storing context in struct
type Service struct {
    ctx context.Context  // Don't do this!
    db  *sql.DB
}

// ✅ Good - pass context through methods
type Service struct {
    db *sql.DB
}

func (s *Service) GetData(ctx context.Context, id string) (*Data, error) {
    return s.db.QueryContext(ctx, "SELECT...")
}
```

**Exception**: It's acceptable to store context in a struct if it's only for the lifetime of a request (like in HTTP handlers), but even then, prefer passing it explicitly.

## **3. Never Pass nil Context**

Always provide a valid context, even if you don't need its features:


```go
// ❌ Bad
doSomething(nil, data)

// ✅ Good - when you don't have a context yet
doSomething(context.TODO(), data)

// ✅ Better - start with a background context
ctx := context.Background()
doSomething(ctx, data)
```

Use `context.TODO()` when you're refactoring and temporarily don't have a context to pass. Use `context.Background()` for main functions, tests, and initialization code.


#### **7. Check Context Cancellation in Long Operations**

For long-running or iterative operations, periodically check if the context is cancelled:

go

```go
func processLargeDataset(ctx context.Context, data []Item) error {
    for i, item := range data {
        // Check cancellation periodically
        if i%100 == 0 {
            select {
            case <-ctx.Done():
                return ctx.Err()
            default:
            }
        }
        
        if err := processItem(ctx, item); err != nil {
            return err
        }
    }
    return nil
```

#### **8. Respect Context in Goroutines**

When spawning goroutines, pass the context and respect cancellation:

go

```go
func fanOut(ctx context.Context, inputs []string) {
    g, ctx := errgroup.WithContext(ctx)
    
    for _, input := range inputs {
        input := input // Capture loop variable
        g.Go(func() error {
            return process(ctx, input)
        })
    }
    
    if err := g.Wait(); err != nil {
        log.Printf("Error in fanOut: %v", err)
    }
}
```


#### **Create Derived Contexts for Scoped Operations**

Think of context as a tree structure where you can create child contexts with more specific constraints than their parent. Each child inherits the parent's properties but can add its own limitations.

### **The Concept**

When you have a main operation that contains several sub-operations, each sub-operation might need different constraints:

go

```go
func handleUserRequest(ctx context.Context) error {
    // Main operation has 30 seconds total
    ctx, cancel := context.WithTimeout(ctx, 30*time.Second)
    defer cancel()
    
    // But fetching from cache should be quick - only 1 second
    cacheCtx, cacheCancel := context.WithTimeout(ctx, 1*time.Second)
    user, err := fetchFromCache(cacheCtx, userID)
    cacheCancel() // Clean up immediately after use
    
    if err != nil {
        // Cache miss or timeout - try database with 5 seconds
        dbCtx, dbCancel := context.WithTimeout(ctx, 5*time.Second)
        defer dbCancel()
        user, err = fetchFromDB(dbCtx, userID)
        if err != nil {
            return err
        }
    }
    
    // Process the user with remaining time from parent context
    return processUser(ctx, user)
}
```

**Why This Matters?**

Different operations have different acceptable durations:

- **Cache lookups** should be nearly instant (milliseconds)
- **Database queries** might take a few seconds
- **External API calls** could take longer
- **Background processing** might run for minutes

By creating scoped contexts, you prevent slow operations from consuming all available time:


```go
func fetchDataWithFallback(ctx context.Context) (*Data, error) {
    // Try primary service with tight deadline
    primaryCtx, cancel := context.WithTimeout(ctx, 2*time.Second)
    data, err := callPrimaryService(primaryCtx)
    cancel() // Don't defer - we want to clean up immediately
    
    if err == nil {
        return data, nil
    }
    
    // Primary failed, try secondary with remaining time
    // This uses the parent ctx, so it has whatever time is left
    return callSecondaryService(ctx)
}
```

### **Always Call Cancel Functions**

When you create a context with `WithCancel`, `WithTimeout`, or `WithDeadline`, Go returns a cancel function. **Not calling this function causes resource leaks**.

##### **The Problem**

Every time you create a derived context, Go allocates resources to track cancellation. If you don't call cancel, these resources stay in memory:


```go
// ❌ BAD - Resource leak!
func leakyFunction() {
    ctx, _ := context.WithTimeout(context.Background(), 5*time.Second)
    // Never calling cancel means the timer goroutine lives forever
    doSomething(ctx)
}

// After calling this 1000 times, you have 1000 timer goroutines waiting!
```

##### **The Solution**

**Always** call the cancel function, even if the operation completes successfully:

```go
// ✅ GOOD - Always clean up
func properFunction() {
    ctx, cancel := context.WithTimeout(context.Background(), 5*time.Second)
    defer cancel() // This ensures cleanup happens no matter what
    
    err := doSomething(ctx)
    if err != nil {
        return err // cancel() still gets called due to defer
    }
    return nil // cancel() gets called here too
}
```


#### **Why Cancel When Operation Succeeds?**

You might think "if the operation finished successfully, why call cancel?" Here's why:


```go
func whyCancelMatters() {
    ctx, cancel := context.WithTimeout(context.Background(), 10*time.Second)
    // defer cancel() // <- Commenting this out causes a leak
    
    // This operation finishes in 1 second
    quickOperation(ctx)
    
    // Without calling cancel(), the timer goroutine waits the full 10 seconds
    // even though we're done after 1 second!
}
```

##### **Real Impact of Not Calling Cancel**


```go
// This HTTP handler leaks memory on every request!
func leakyHandler(w http.ResponseWriter, r *http.Request) {
    ctx, _ := context.WithTimeout(r.Context(), 30*time.Second)
    // Missing cancel!
    
    data, _ := fetchData(ctx)
    json.NewEncoder(w).Encode(data)
}

// After 10,000 requests, you have 10,000 goroutines waiting to timeout!
// Memory usage grows continuously until the server crashes
```

##### **Correct Implementation**

```go
func properHandler(w http.ResponseWriter, r *http.Request) {
    ctx, cancel := context.WithTimeout(r.Context(), 30*time.Second)
    defer cancel() // This one line prevents the memory leak
    
    data, err := fetchData(ctx)
    if err != nil {
        http.Error(w, err.Error(), 500)
        return // cancel() is still called thanks to defer
    }
    json.NewEncoder(w).Encode(data)
}
```
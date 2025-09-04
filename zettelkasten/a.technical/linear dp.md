---
tags:
  - dynamic-programming
  - problem-solving
parent: "[[dp common patterns and problems]]"
type: permanent
---

Linear DP is one of the most fundamental DP patterns where you solve problems by making decisions at each position and building up solutions from smaller subproblems.

1D array, each element depends on previous elements.
examples are
- Fibonacci Numbers Problem 
	- state: `dp[i] = dp[i-1] + dp[i-2]`
- **Coin Change (LeetCode 322)**
	- state `dp[i] = min(dp[i], dp[i-coin] + 1)`
- **Climbing Stairs (LeetCode 70)**
	- `dp[i] = dp[i-1] + dp[i-2]`
- **House Robber (LeetCode 198)**
	- `dp[i] = max(dp[i-1], dp[i-2] + nums[i])`
- More problems and Examples https://neetcode.io/roadmap 


## Core Concept

**The key insight**: At each position `i`, you have a **choice** to make, and the optimal solution depends on:

1. The **current element** at position `i`
2. The **optimal solutions** from previous positions

```
ALGORITHM LinearDP
INPUT: array of elements
OUTPUT: optimal value

1. INITIALIZE dp array or variables
2. SET base cases (usually dp[0] or first few elements)
3. FOR each position i from base case to end DO
   4. FOR each possible choice at position i DO
      5. CALCULATE result if we make this choice
      6. UPDATE dp[i] with optimal choice
   5. END FOR
6. END FOR
7. RETURN dp[last_position] or global optimum
```

### Common Decision Types

### 1. **Include vs Exclude** / Take It or Leave It
- **Example**: [[house robber 2 dp problem]], Maximum Sum Non-Adjacent Elements
- **Choices**: Take current element or skip it
- **Recurrence**: `dp[i] = max(dp[i-1], nums[i] + dp[i-2])`
### 2. **Extend vs Start New** / Continue or Reset
- **Example**: Maximum Subarray (Kadane's Algorithm)
- **Choices**: Extend previous subarray or start new one
- **Recurrence**: `dp[i] = max(nums[i], dp[i-1] + nums[i])`
### 3. Multiple Choices / Pick Best Option

- **Example**: [[coin change dp problem]], Jump Game
- **Choices**: Try all possible moves/coins
- **Recurrence**: `dp[i] = min/max(dp[i-choice] + cost) for all choices`



### Step-by-Step Problem-Solving Process

#### Step 1: Identify the Problem Type
Ask yourself:
- Can I break this into smaller subproblems?
- Does the optimal solution depend on decisions at each position?
- Are there overlapping subproblems?
#### Step 2: Define the State
- **What does `dp[i]` represent?**
- Common definitions:
    - `dp[i]` = optimal value ending at position `i`
    - `dp[i]` = optimal value for first `i` elements
    - `dp[i]` = optimal value starting from position `i`
### Step 3: Identify the Choices
- What decisions can you make at each position?
- How do these choices affect the result?
### Step 4: Write the Recurrence Relation
- How does `dp[i]` relate to previous states?
- Consider all possible choices and pick the optimal one
### Step 5: Handle Base Cases
- What are the simplest cases?
- Usually `dp[0]` or first few elements
### Step 6: Determine the Final Answer
- Is it `dp[n-1]`, `dp[n]`, or do you need to check all positions?



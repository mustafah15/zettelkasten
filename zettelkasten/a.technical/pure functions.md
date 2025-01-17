---
tags:
  - fp
  - software-design
type: permanent
parent: "[[functional programming]]"
---
A **pure function** is a function that adheres to these two rules:
1. **Deterministic Behavior**:
    - Given the same inputs, a pure function always returns the same output.
    - There are no variations or randomness in its behavior.
2. **No Side Effects**:
    - A pure function does not modify external state or variables.
    - It does not depend on external state that might change.

#### **Characteristics of Pure Functions**
- No reliance on global variables or mutable data.
- No modification of data outside the function's scope.
- No input/output operations (e.g., logging, file handling) within the function.


#### **How to Use Pure Functions in Your Code**
1. **Identify Side Effects**: Refactor functions to avoid modifying external state.
2. **Use Functional Programming Principles**:
    - Favor immutability over mutability.
    - Avoid operations like logging, API calls, or DOM manipulation in pure functions.
3. **Combine Pure Functions**: Use tools like `map`, `filter`, and `reduce` to work with pure logic.


example of a pure function


```javascript
let globalValue = 10;

// Impure function (modifies external state)
function impureMultiplyByTwo(x) {
    globalValue = globalValue * 2; // Side effect
    return x * 2;
}

// Pure function
function pureMultiplyByTwo(x) {
    return x * 2;
}

console.log(pureMultiplyByTwo(5)); // Output: 10
console.log(globalValue); // Remains unchanged at 10

```

#### Function Composition 

Pure functions can be composed to build more complex operations.

```javascript 
const add5 = x => x + 5;
const multiplyBy3 = x => x * 3;

// Compose pure functions
const addThenMultiply = x => multiplyBy3(add5(x));

console.log(addThenMultiply(2)); // Output: 21 ((2 + 5) * 3)

```

#### Avoiding Mutability

```javascript
const person = { name: "Alice", age: 25 };

// Pure function to update age
function updateAge(person, newAge) {
    return { ...person, age: newAge }; // Returns a new object
}

const updatedPerson = updateAge(person, 30);

console.log(updatedPerson); // Output: { name: "Alice", age: 30 }
console.log(person); // Original object remains unchanged: { name: "Alice", age: 25 }

```
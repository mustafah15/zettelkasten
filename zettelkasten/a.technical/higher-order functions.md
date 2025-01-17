---
tags:
  - software-design
  - "#fp"
type: permanent
parent: "[[functional programming]]"
---
a **higher-order function** is a function that either:

1. **Takes one or more functions as arguments**, or
2. **Returns a function as its result**.

This concept leverages JavaScript's ability to treat functions as **first-class citizens**, meaning functions can be assigned to variables, passed as arguments, and returned from other functions.


#### **Benefits of Higher-Order Functions**
1. **Code Reusability**: Common behaviours can be abstracted and reused.
2. **Modularity**: Functions can be composed to handle specific tasks.
3. **Readability**: Clear separation of logic by using smaller, single-purpose functions.


#### **Examples of Higher-Order Functions**

**1. Taking Functions as Arguments**

Higher-order functions can take other functions as parameters to perform dynamic operations.

```javascript
// Example 1: Using `map` to transform an array
const numbers = [1, 2, 3, 4];
const squares = numbers.map(num => num * num); // Function passed to `map`
console.log(squares); // Output: [1, 4, 9, 16]

// Example 2: Using `filter` to select specific values
const evenNumbers = numbers.filter(num => num % 2 === 0); // Function passed to `filter`
console.log(evenNumbers); // Output: [2, 4]

// Example 3: Using `reduce` to accumulate a value
const sum = numbers.reduce((acc, num) => acc + num, 0); // Function passed to `reduce`
console.log(sum); // Output: 10

```


 **2. Returning Functions**

Higher-order functions can return other functions, enabling dynamic behavior.

```javascript
// Function that creates a multiplier
function createMultiplier(factor) {
    return function (number) {
        return number * factor;
    };
}

const double = createMultiplier(2); // Returns a function that doubles
const triple = createMultiplier(3); // Returns a function that triples

console.log(double(5)); // Output: 10
console.log(triple(5)); // Output: 15

```



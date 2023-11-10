---
tags:
  - tools
type:
  - literature
related: "[[TypeScript|TS]]"
---
Another common primitive is the number. Since TypeScript is a superset of JavaScript, numbers work the same way in both languages. The openness of JavaScript allows for a broad set of numbers. Integers, signed floats, or unsigned floats are permitted. By default, a number will be base 10.

When a type is explicitly assigned to a variable, the type will be removed once the JavaScript is generated. The reason is that typing does not exist in JavaScript. It explains why TypeScript only has `number`. The following code will produce three variables without an explicit type in JavaScript but if `typeof` is used, it will return the dynamic type: `number`.

## The `number`: integer, decimal, and signed

The `number` type is the same as in JavaScript: it defines the type for integer, float, double, etc. So integer, float, and positive or negative numbers will all be referred to as the single type, `number`. A type declared as `number` (implicitly or explicitly) can be checked at runtime as well with `typeof` which will return `number`.

Numbers are also not signed. This means they can be positive or negative.

```typescript

let int: number = 1;
let float: number = 1.1; 
let negative: number = -100;

console.log(typeof(int)); //number
console.log(typeof(float)); //number
console.log(typeof(negative)); //number

```
In TypeScript, as in JavaScript, the type `number` can be assigned with `NaN` meaning that it is not a number.

## NaN

In TypeScript, as in JavaScript, the type `number` can be assigned with `NaN` meaning that it is not a number.

```typescript

let myNumberIsNotANumber: number = NaN;
console.log(typeof(myNumberIsNotANumber)); // number

```

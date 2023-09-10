
tags: #tools 
type: #fleeting 
related: [[TypeScript]]

---

Type Annotation: a code that we add to tell the TypeScript compiler what type of value a variable will refer to.

annotation for primitives is simple and should be done like this 

```ts

// <const,let,var><variable-name> : <varible-type> = <optional init value>;

let apples: number = 5;

let speed: string = 'fast';

let hasName: boolean = true;

let nothingMuch: null = null;

let nothing: undefined = undefined;

// Array of strings
let colors: string[] = ['red', 'green', 'blue'];

// Class and instance of a class

class Car {}

let car: Car = new Car();

// Object literal
let point: { x: number; y: number } = {
x: 10,
y: 20,
};


// Function
const logNumber: (i: number) => void = (i: number) => {
	console.log(i);
};

```



Type Inference: Typescript tries to figure out what type of value a variable refers to. 

If variable declaration and initialization are on the same line typescript will figure out the type of the variable for us. If this happens in different lines or steps the TS compiler will set the type of the variable to `any` 

#### What Is any Type?

If the TypeScript compiler is not able to type inference a variable it will set it to the type of `any` that tells that the compiler has no clue at all what this variable type is.
we should avoid variables of any type at all costs because the main idea of TS is leveraging its type-checking system.
#### When To Use Type Annotations

- function that returns the type `any`
	- then we need to interfere and define the type of the returned value In the following example see how we interfered and added a type to coordinates object to prevent typescript from assigning it to any.
``` ts
	const str = '{"x": 10, "y": 20}';
	
	let coordinates: {x: number, y: number} = JSON.parse(str);
```
- Delayed initialization or when we declare a variable on one line and initialize it later.
- variable whose type can't be inferred correctly 



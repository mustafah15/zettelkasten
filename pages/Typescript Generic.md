---
title: Typescript Generic
---

- Generic allows for improved reusability by parameterizing a type with another one. A popular front-end framework named React can have an unlimited number of components. They all have properties that are unique to their components. It would be tedious to have to inherit a base class or alter the framework to accommodate all potentials possibilities. Hence, the properties of these React components use a generic.

- 
```typescript
class ArrayOfAnything<T> {
  constructor(public collection: T[]) {}
  get(index: number): T {
    return
  }
}
```

- Generic vs any
	 - Generic is not required in JavaScript or even before TypeScript implemented the notion of generic since you can use the loose type, `any`  The drawbacks of any are that you cannot constrain the type passed to your class to have a minimal definition and you will have to cast back once the data once it is extracted from your class.

	 - When using any you'll lose all type checking and safety checking that Typescript is offering, whereas, T behaves like a variable that will hold the Type that you don't know what it is going to be.

- Generic without classes 
	 - 
```typescript
function countElementInArray<T>(elements: T[]): number {
    return elements.length;
}

function returnFirstElementInArray<T>(elements: T[]): T | undefined {
    if (elements.length > 0) {
        return elements[0];
    }
    return undefined;
}
const arr = [1, 2, 3];
console.log(countElementInArray(arr));
console.log(returnFirstElementInArray(arr));
```

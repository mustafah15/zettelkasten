---
tags:
  - tools
parent: "[[TypeScript|TS]]"
type: permanent
---


 Maybe we should start talking about the type system by asking what is a type in the first place. a type is a property that tells you and your compiler what kind of variable this is, right? 
 now we can ask what is a type system? why do we need it?

>wiki def:  a **type system** is a logical system comprising a set of rules that assigns a property called a type (for example, integer, floating point,  string to every "term" (a word, phrase, or other set of symbols).

so for any programming language, if I declared a variable that holds a string, I can apply string rules (operations) to it (split, concat, print, .. etc.) and for example, if you have a boolean variable you can't apply string rules on it for example split.
It's really important for a language compiler to know the difference between types to know which rules would apply to this specific variable or which type rules will be applied to it.

we can define a type in a nutshell as an easy way to refer to the different properties and functions that a value has 

#### Does JS Has A Type System?
Of course it has JS has variables with different types like string, number, boolean, undefined, function, null, symbol, and object which can be (array, object, or data) 
but programming languages can have strong type systems and weak type systems, in a strong type system you have to declare explicitly your variable type however in a weak type system like JS it's implicitly assigned by the compiler 
#### What does TS Provide On Top Of That?

**TypeScript's type** system is a static type system, meaning that the types are checked at compile time rather than runtime. TypeScript offers a variety of primitive types, such as boolean, number, string, null, and undefined, as well as complex types such as classes, interfaces, enums, and tuples.

In addition, TypeScript also supports type inference, which allows the compiler to automatically deduce the type of a variable based on its value. TypeScript's type system also supports type guards, which are used to narrow down the possible types of a value within a block of code.

Another key feature of TypeScript's type system is its support for generics, which allows for the creation of reusable code that can work with a variety of different types. Additionally, TypeScript's type system also supports union types and intersection types, which allow for the creation of types that combine multiple types into a single type.

### TypeScript's Primitive Types

Primitive types in TypeScript are the most basic data types that can be used to define variables and functions. Here's a more detailed explanation of each primitive type:

1. `boolean`: Represents a logical value that can be either `true` or `false`.
2. `number`: Represents a numeric value, which can be either an integer or a floating-point number.
3. `string`: Represents a sequence of characters that represents text.
4. `null`: Represents the intentional absence of any object value.
5. `undefined`: Represents a variable that has not been assigned a value.

These primitive types are used to represent simple data types in TypeScript and can be used to define variables and function parameters.

### TypeScript's Object Types

In addition to primitive types, TypeScript also supports more complex types that provide more advanced functionality for defining custom data types. Here's a more detailed explanation of each complex type:

1. `Classes`: Classes are used to define objects with properties and methods. They can be used to represent real-world objects or entities in a software system. Classes in TypeScript follow the same syntax as classes in other object-oriented programming languages, such as Java or C#.
2. `Interfaces`: Interfaces define a contract for an object's properties and methods. They can be used to define the shape of an object without having to create a class. Interfaces in TypeScript can also be used to extend existing interfaces or classes.
3. `Enums`: Enums are used to define a set of named constants. They can be used to improve the readability and maintainability of code by giving names to specific values. Enums in TypeScript can be defined using either numeric or string values.
4. `Tuples`: Tuples are used to represent an array with a fixed number of elements, each of which can be a different type. They can be used to represent data that has a specific order and type. Tuples in TypeScript are defined using square brackets and a comma-separated list of types.

Using these complex types, developers can create more sophisticated data structures that better reflect the needs of their application. 

|Type|Description|
|---|---|
|boolean|A logical value that can be either true or false.|
|number|A numeric value, which can be either an integer or a floating-point number.|
|string|A sequence of characters that represents text.|
|null|A special value that represents the absence of any object value.|
|undefined|A special value that represents a variable that has not been assigned a value.|
|any|A type that represents any value.|
|void|A type that represents the absence of a value.|
|object|A type that represents any non-primitive value.|
|array|An ordered list of values, all of which must be of the same type.|
|tuple|A type that represents an array with a fixed number of elements, each of which can be a different type.|
|enum|A type that represents a set of named values.|
|function|A type that represents a function.|
|interface|A type that defines a contract for an object's properties and methods.|
|class|A type that represents an object with properties and methods.|


### TypeScript's Type System Is A Type Inference System

TypeScript's type system includes support for type inference, which allows the compiler to automatically deduce the type of a variable based on its value. This means that developers can often avoid having to explicitly specify the type of a variable, and instead let the compiler infer the type automatically.

Type inference is particularly useful when working with complex data structures or when using higher-order functions. For example, consider the following TypeScript code:

```ts
const myArray = [1, 2, 3];
const sum = myArray.reduce((acc, val) => acc + val, 0);
```

**In this code**, we define an array of numbers and then use the `reduce` method to calculate the sum of all the elements in the array. Notice that we did not explicitly specify the type of the `myArray` variable or the parameters of the `reduce` method. TypeScript's type system is able to automatically infer that `myArray` is an array of numbers and that the `acc` and `val` parameters of the `reduce` method are also numbers.

Type inference can also be useful when working with functions that return values of different types depending on their input. For example, consider the following TypeScript code:

```ts
function add(a: number, b: number) {
  return a + b;
}

const result = add(1, 2);
```

**In this code**, we define a function called `add` that takes two numbers as parameters and returns their sum. Notice that we explicitly specify the types of the `a` and `b` parameters. However, we do not need to specify the type of the `result` variable, as TypeScript's type system is able to automatically infer that it is a number based on the return type of the `add` function.

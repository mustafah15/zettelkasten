---
tags:
  - tools
type:
  - literature
related: "[[TypeScript|TS]]"
---
An `enum` is a structure that proposes several allowed values for a variable. It is a way to constrain variable values by defining specific possible entries.

## `enum` with values

`enum` can be of `string` type. In that case, every member requires a value without exception.

```typescript

enum MyStringEnum {
    ChoiceA = "A",
    ChoiceB = "B",
}

```



A mixed `enum` value type is acceptable if every member is defined. For example, you can have one item be an integer and another be a string type. It is recommended not to mix types since it might be more confusing than pragmatic.
```typescript
enum MyStringAndNumberEnum {     

    ChoiceA, // 0     
    ChoiceB = "B",     
    ChoiceC = 100 
}

```


## `enum` without values
`enum` is a type that enforces a limited and defined group of constants. `enum` must have a name and accepted values. Afterward, you can use the `enum` as a type. The consumer must use the `enum` with its name followed by a dot and a potential value from the defined list.

```typescript

enum MyEnum {
ChoiceA,
ChoiceB,
ChoiceC,
}

let x: MyEnum = MyEnum.ChoiceA;
console.log(x); //0


```

The values are all constants starting from 0 for the first item and increasing by one until the end. This type of `enum` has **implicit** value. Developers can specify a specific value by equating it to an integer. In that case, the `enum` is **explicit**.

```typescript

enum MyEnum {
ChoiceA,
ChoiceB,
ChoiceC,
}

enum MyEnum2 {
ChoiceA, // 0
ChoiceB = 100, // 100
ChoiceC, // 101
ChoiceD = MyEnum.ChoiceC, // 2
}

console.log(MyEnum2.ChoiceA); // 0
console.log(MyEnum2.ChoiceB); // 100
console.log(MyEnum2.ChoiceC); // 101
console.log(MyEnum2.ChoiceD); // 2 

```


`enum` members’ values can be set directly or by using computation. There are two types of computation:

1. a constant one
2. a purely computed one

A computed constant is a value provided by another `enum` or a value computed by addition, subtraction, bitwise, modulo, multiplication, division, “or,” “and,” “xor” operator, or complement operator (~). Purely computed values come from a **function**.

`enum` generates a function in JavaScript with a set that allows us to specify the number or name used to access the value. Here is the output of the two previously studied `enum`:


```typescript
/*

enum MyEnum {

ChoiceA,

ChoiceB,

ChoiceC,

} */

// Became in JavaScript:

  

var MyEnum;

(function (MyEnum) {

MyEnum[MyEnum["ChoiceA"] = 0] = "ChoiceA";

MyEnum[MyEnum["ChoiceB"] = 1] = "ChoiceB";

MyEnum[MyEnum["ChoiceC"] = 2] = "ChoiceC";

})(MyEnum || (MyEnum = {}));

  

/*

enum MyEnum2 {

ChoiceA, // 0

ChoiceB = 100, // 100

ChoiceC, // 101

ChoiceD = MyEnum.ChoiceC, // 2

}

*/

  

//Because in JavaScript

var MyEnum2;

(function (MyEnum2) {

MyEnum2[MyEnum2["ChoiceA"] = 0] = "ChoiceA";

MyEnum2[MyEnum2["ChoiceB"] = 100] = "ChoiceB";

MyEnum2[MyEnum2["ChoiceC"] = 101] = "ChoiceC";

MyEnum2[MyEnum2["ChoiceD"] = 2] = "ChoiceD";

})(MyEnum2 || (MyEnum2 = {}));

```

## `enum` with bitwise values

`enum` is a good candidate for _bitwise operations_ since the value can be explicitly set (value set during the definition of the `enum`) and you can use the bit shift operator. Once defined, you can use it as any variable to determine if it contains the one you need or use the ampersand (`&`) to check if the one you want is present. The pipe symbol (`|`) lets you add many `enum` choices to a variable.
he following code not only initializes the value with the `|` but also checks the value. With bitwie, we cannot directly use an equal sign. The reason is that bitwise operation returns a number, not a boolean. Hence, we need to compare the number to the desired comparison value. Line 10 demonstrates how to check the value of an `enum`.

```typescript

enum Power {

None = 0, // Value 0 in decimal (00 in binary)

Invincibility = 1 << 0, // Value 1 in decimal (01 in binary)

Telepathy = 1 << 1, // Value 2 in decimal (10 in binary)

Invisibility = 1 << 2, // Value 4 in decimal (100 in binary)

Everything = Invincibility | Telepathy | Invisibility,

}

let power: Power = Power.Invincibility | Power.Telepathy;

console.log("Power values:" + power); // 3

if (Power.Telepathy === (power & Power.Telepathy)) {

console.log("Power of telepathy available"); //Power of telepathy available

}
```

The value of the previous example is 3 because the `Invincibility` value is `1<<0`, which is binary `01`.
The `Telepathy` value is `1<<1` which gives the binary `10` and the `or` operation provided by the pipe symbol gives binary `11` which is `3`.

It is possible to remove a value from a bitwise `enum` on the fly by using `&= ~` which performs an `and` operation on the inverse of the value.
For example, the following code supplements the previous example by removing the `Telepathy` power.

```typescript
enum Power {

None = 0, // Value 0 in decimal (00 in binary)

Invincibility = 1 << 0, // Value 1 in decimal (01 in binary)

Telepathy = 1 << 1, // Value 2 in decimal (10 in binary)

Invisibility = 1 << 2, // Value 4 in decimal (100 in binary)

Everything = Invincibility | Telepathy | Invisibility,

}

let power: Power = Power.Invincibility | Power.Telepathy;

console.log("Power values:" + power);

if (Power.Telepathy === (power & Power.Telepathy)) {
	console.log("Power of telepathy available");
}

power &= ~Power.Telepathy;

console.log("Power values:" + power);

if (Power.Telepathy === (power & Power.Telepathy)) {
	console.log("Power of telepathy available");
}


//output

// Power values:3 
// Power of telepathy available
// Power values:1

```

The value is `1` because from the `3`, (which is in binary `11`) you use the inverse of `10` which is `01`. `11, and 01 = 01` which is 1.

# Accessing Enum Values
A variable set with an `enum` that has a `number` lets you access the `enum` name from the integer. However, an `enum` with string values does not have this capability. This means you can use the `enum` name followed by the name of the constant to get the value. Also, with a number, you can also use the value to return the name.

For example, an `enum` called `Orientation` with `East`, `West`, `North`, `South` could use `Orientation.East` to get the value zero or use `Orientation[0]` to get `East`. This works because TypeScript generates a map object that gives you access using the name of the entry _or_ the value.

Here is the generated code of the orientation `enum`:
```typescript

enum Orientation {
East,
West,
North,
South,
}

let directionInNumber = Orientation.East; // Access with the Enum
let directionInString = Orientation[0]; // Access the Enum string from number


```

# Speeding Up Enum

## Setting `enum` as `const` to increase speed

`enum` can be set as a constant to speed up the performance. This way, during execution, instead of referencing the function generated by TypeScript to JavaScript, it will use the value.

For example, without constant `enum`, the value set to a direction with `Orientation.East` will be equal to a function that looks for the value in the map to get the value. However, with a constant, the value is set in the transpiled code to `0` directly – no more function or mapping.

## Drawbacks

There are not a lot of drawbacks to this. You can still use the `enum` with the dot notation and the name of one of the entries. You can also use the name of the `enum` with the square brackets and the name of one of the entries.

However, you won’t be able to use the square brackets with the value.

The only difference is that a constant `enum` doesn’t allow for redefining values once they’re initialized, which is allowed with default non-constant `enum`. However, in both cases, it’s possible to add an entry using the square brackets.

# Merging and Adding Functionality to Enum

## Merging values

Like interfaces, an `enum` can be defined in more than one place. You can start defining the `enum` and later define it again. In the end, all values merge into a single `enum`. There is one constraint with multiple definitions of a single `enum`: the first value of every `enum` must have an explicit value. If an explicit value is defined twice, only the last value will be associated with the `enum` when using the reverse value to find an `enum`. Listing the same value twice is not a feature of multiple definitions; a single enumeration definition can have several entries with the same values as well.
```typescript

enum EnumA {
ChoiceA,
}

enum EnumA {
ChoiceB = 1,
}

  

let variable1: EnumA = EnumA.ChoiceA;
console.log(variable1); //0

variable1 = EnumA.ChoiceB;
console.log(variable1); //1
```

## Adding Functions 
Another feature of `enum` is that you can attach functions that will be accessible statically by the `enum`. Using an `enum` with a function means that you can use `Orientation.East` as well as `Orientation.yourFunction`. Defining a function inside an `enum` requires the use of a namespace with an exported function.

```typescript

enum Orientation {
	East,
	West,
	North,
	South,
}

namespace Orientation {
	export function yourFunction() {
		console.log("I am in a Enum");
	}
}

Orientation.yourFunction();

```

the generated JS code looks like this 
```typescript
(function (variableEnumFunctions) {

let Orientation;

(function (Orientation) {

Orientation[Orientation["East"] = 0] = "East";

Orientation[Orientation["West"] = 1] = "West";

Orientation[Orientation["North"] = 2] = "North";

Orientation[Orientation["South"] = 3] = "South";

})(Orientation || (Orientation = {}));

(function (Orientation) {

function yourFunction() {

console.log("I am in an Enum");

}

Orientation.yourFunction = yourFunction;

})(Orientation || (Orientation = {}));

Orientation.yourFunction();

})(variableEnumFunctions || (variableEnumFunctions = {}));
```

As you can see, the final product is that an `enum` is a function that wraps other functions. Hence, it is possible to add functions to an `enum`.

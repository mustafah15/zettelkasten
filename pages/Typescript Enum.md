---
title: Typescript Enum
---

- Enum with values
	 - enum can be of string type. In that case, every member requires a value without exception.

	 - 
```typescript
enum MyStringEnum {
    ChoiceA = "A",
    ChoiceB = "B",
}
```

	 - A mixed enum value type is acceptable if every member is defined. For example, you can have one item be an integer and another be a string type. It is recommended not to mix types since it might be more confusing than pragmatic.

	 - 
```typescript
enum MyStringAndNumberEnum {     
    ChoiceA, // 0     
    ChoiceB = "B",     
    ChoiceC = 100 
}
```

- Enum without. values 
	 - enum is a type that enforces a limited and defined group of constants. enum must have a name and accepted values. Afterward, you can use the enum as a type. The consumer must use the enum with its name followed by a dot and a potential value from the defined list.

	 - 
```typescript
enum MyEnum {
    ChoiceA,
    ChoiceB,
    ChoiceC,
}
let x: MyEnum = MyEnum.ChoiceA;

```

- Accessing Enum Values
	 - A variable set with an enum that has a number lets you access the enum name from the integer. However, an enum with string values does not have this capability. This means you can use the enum name followed by the name of the constant to get the value. Also, with a number, you can also use the value to return the name.

	 - For example, an enum called Orientation with East, West, North, South could use Orientation.East to get the value zero or use Orientation[0] to get East. This works because TypeScript generates a map object which gives you access using the name of the entry __or__ the value.

	 - 
```javascript
enum OrientationString {
    East = "E",
    West = "W",
    North = "N",
    South = "S",
}
let directionInNumber = OrientationString.East; // Access with the Enum
let directionInString = OrientationString[0];  // Access the Enum string from number
let directionInString2 = OrientationString["E"];  // Access the Enum string from number
console.log(directionInNumber);
console.log(directionInString);
console.log(directionInString2);
```

	 - As mentioned, it is not possible with an enum that has strings for value. The following code does not compile because lines 8 and 9 wrongly accessed the enum.

- Adding functions
	 - Another feature of enum is that you can attach functions that will be accessible statically by the enum. Using an enum with a function means that you can use Orientation.East as well as Orientation.yourFunction. Defining a function inside an enum requires the use of a namespace with an exported function.

	 - 
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

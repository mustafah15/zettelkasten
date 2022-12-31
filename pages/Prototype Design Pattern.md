---
title: Prototype Design Pattern
---

- What is the prototype pattern?
id:: 68b101d1-12e4-4702-86df-d435f290d824
	 - The **prototype creational pattern** is used to instantiate objects with some default values using an existing object. It clones the object and provides the existing properties to the cloned object using prototypal inheritance.
id:: dd96fdb4-c69a-4934-978e-2dfb4e5c77cf

	 - In prototypal inheritance, a prototype object acts as a blueprint from which other objects inherit when the constructor instantiates them. Hence, any properties defined on the prototype of a constructor function will also be present in the cloned object it creates.
id:: b3777d6a-dc1e-490d-bd42-097d4fac68e6

	 - In JavaScript, objects can be cloned using the Object.create method. Let’s look at it in detail in the example below.

```javascript
var car = {
    drive(){
        console.log("Started Driving")
        },
    brake(){
        console.log("Stopping the car")
    },
    numofWheels : 4  
} 

const car1 = Object.create(car);
car1.drive();
car1.brake();
console.log(car1.numofWheels);

const car2 = Object.create(car)
car2.drive();
car2.brake();
console.log(car2.numofWheels);
```
id:: 1492769a-44ed-4508-a419-ea0dd51b4ce2

	 - When to use the prototype pattern?
id:: de0ea153-7276-47ac-a24d-7a5d7fad4652
		 - The prototypal pattern has native support in JavaScript. It involves cloning an already-configured object. Hence, the cloned objects are created by reference instead of having their own separate copies. This boosts the performance and efficiency of code. This pattern can also be used in the following cases:
id:: e2343185-97fc-4d4b-a3ce-2a4cb1a1a091
			 - To eliminate the overhead of initializing an object
id:: 98034c2e-1fc3-42e6-b532-fd80ec4aa8c3

			 - When you want the system to be independent about how the products in it are created
id:: f20e58a3-3d83-4dc5-8809-65bbeaa03ea5

			 - When creating objects from a database, whose values are copied to the cloned object
id:: eea9d791-d40c-49ec-9180-9b2385423436

	 - 
id:: d706ee7f-5756-4f47-a7b7-cea5ee001b8b

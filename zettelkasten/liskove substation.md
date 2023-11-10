---
tags:
  - software-design
  - oop
type:
  - fleeting
related: "[[SOLID]]"
---


tags: #oop #software-design 
type:  #fleeting

statement: __in any object-oriented program, if we substitute a superclass object  with an object of any of its subclasses, the program should not break.__

Example

Let's construct a simple class called `Vehicle` that has some attributes and methods and a subclass `Car` that extends it.
So far, this implementation seems right since a car IS A vehicle, and the `startEngine()` method will override the superclass method. However, it's not as simple as it looks.
Let's add a `Bicycle` subclass in this system and see what happens:
This results in a problem. A bicycle is a vehicle, but it does not have an engine. Therefore, the `Bicycle` class should not be allowed to override the `startEngine()` method.
A possible fix to this issue would be to add two subclasses of `Vehicle` that classify the vehicles as motorized vehicles and manual vehicles:

With this implementation, we have satisfied the LSP.
- `Car` is substitutable with its superclass, `Motorized`, and `Bicycle` is substitutable with its superclass, `Manual`, without breaking the functionality.
- Their methods can also override the methods of the superclass.


The LSP is an important principle that should be extended to the level of system architecture. A small violation of the substitutability of classes can cause the system to break down, which is why we should always be on the lookout for violations. A few benefits of the LSP are provided below:

- It avoids the generalization of concepts that may not be needed in the future.
- It makes the code maintainable and easier to upgrade.
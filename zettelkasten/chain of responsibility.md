---
tags:
  - design-patterns
  - software-design
  - oop
related: "[[design patterns]]"
type:
  - fleeting
aliases:
  - chain of responsibility design pattern
---
- What is the chain of responsibility pattern?

- The **chain of responsibility** pattern allows a request sent by a client to be received by more than one object. It creates a chain of loosely-coupled objects that, upon receiving the request, either handle it or pass it to the next handler object.
- A common example of this pattern is __event bubbling__ in [DOM](https://www.educative.io/edpresso/what-is-dom). An event propagates through different nested elements of the DOM until one of them handles it.
- In plain words:

- It helps build a chain of objects. Request enters from one end and keeps going from object to object till it finds the suitable handler.

- Wikipedia says:

- In object-oriented design, the chain-of-responsibility pattern is a design pattern consisting of a source of command objects and a series of processing objects. Each processing object contains logic that defines the types of command objects that it can handle; the rest are passed to the next processing object in the chain.

- When to use the chain of responsibility pattern?

- You can use it if your program is written to handle various requests in different ways without knowing the sequence and type of requests beforehand. It allows you to chain several handlers, thus, allowing all of them a chance to process the request.

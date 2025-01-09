---
tags:
  - software-design
type: literature
parent: "[[benefits of code consistency]]"
---


- names [[names should be consistent|names should be consistent]]
- coding styles. it's common nowadays for development organizations to have style guides that restrict program structure beyond the rules enforced by compilers.
- Interfaces: An interface with multiple implementations is another example of consistency once you understand one implementation of the interface any other implementation becomes easier to understand because you already know the features it will have to provide.
- Design patterns: Design patterns are generally accepted solutions to certain common problems such as the model view controller approach to user interface design. if you can use an existing design pattern to solve the problem the implementation will proceed more quickly it is more likely to work and your code will be more obvious to readers.
- Invariants. An Invariant is a property of a variable or structure that is always true for example, a data structure storing limes of text might enforce an invariant that each line is terminated by a new line character. Invariants reduce the number of special cases that must be considered in code and make it easier to reason about the code's behavior.
---
tags:
  - system-design
type:
  - literature
related: "[[philosophy of software design]]"
---
a software system is divided into modules such as classes in an object-oriented language the modules are designed to be relatively independent of each other so that a programmer can work on the module without having to understand the details of other modules.

in modular design, a software system is decomposed into a collection of modules that are relatively independent. Modules can take many forms, such as classes subsystems, or services, In an ideal world each module would be completely independent of the others a developer could work in any of the modules without knowing anything about any of the other modules. In this world, the complexity of the system would be the complexity of its worst module.
unfortunately, this ideal is not achievable, modules must work together by calling each other's functions or methods. As a result, modules must know something about each other there will be dependencies between the modules if one module changes other modules may need to change to match
The goal of modular design is to minimize the dependencies between modules as Dependencies can take many other forms and can be quite subtle, in order to manage dependencies, we think of each module in two parts an interface and an implementation.
- ![[module interface]]
- ![[module implementation]]
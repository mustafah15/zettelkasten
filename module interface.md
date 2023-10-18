---
tags:
  - system-design
type:
  - literature
related: "[[POSD - complexity in software design]]"
---
A Module Interface consists of everything that a developer working in a different module must know in order to use the given module. Typically the interface describes what the module does but not how it does it.

The interface to a module contains two kinds of information
- **formal**: the formal part of an interface is specified explicitly in the code, and some of these can be checked for correctness by the programming language. for example, the formal interface for a method is its signature. interface for a class consists of the signatures for all of its public methods, plus the names and the types of any public variables.
- **informal**: each interface also includes informal elements that are not specified in the way of an interface including its high-level behavior, such as the fact that a function deletes the fine named by one of its arguments. if there are constraints on the usage of a class these are also part of the class interface. In most interfaces, the informal aspects are larger and more complex than the formal aspects. One of the benefits of a clearly specified interface is that it. indicates exactly what developers need to know in order to use the associated module this helps to eliminate the [[unknown unknowns]]
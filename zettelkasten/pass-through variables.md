---
tags:
  - book-notes
  - software-design
type:
  - literature
related: "[[POSD - different layer different abstraction]]"
---
Another form of API duplication across layers is a pass-through variable which is a variable that is passed down through a long chain of methods.

### why do pass-through variables add complexity?
because they force all of the intermediate methods to be aware of their existence, even though the methods have no use for the variables. furthermore, if a new variable comes into existence you may need to modify a large number of interfaces and methods to pass the variable through all of the relevant paths.

Eliminating pass-through variables.
- One approach is to see if there's already an object shared between the topmost and bottommost methods, if so you can store the variable information in this shared place so you don't need to pass it through all the way down.
- Another approach is to store the information in a global variable this avoids the need to pass the information from method to method but global variables almost create other problems.

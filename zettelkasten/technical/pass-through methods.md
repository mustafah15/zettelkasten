---
tags:
  - book-notes
  - software-design
type:
  - literature
related: "[[POSD - different layer different abstraction]]"
---
When adjacent layers have similar abstractions, the problem often manifests itself in the form of pass-through methods.

The definition of a pass-through method is o**ne that does little except invoke another method whose signature is similar or identical to that of the calling methods**.

If a pass-through method does nothing except pass its arguments to another method, usually with the same API as the pass-through method. this indicates that there is not a clean division of responsibility between the classes.

## why pass-through methods are bad
- They make classes shallower, they increase the interface complexity of the class. but they don't increase the total functionality of the system.
- pass-through methods also create dependencies between classes: if the signature of one layer changes other has to follow the update.

The **solution** is to refactor the classes so that each class has a distinct and coherent set of responsibilities.
one approach is to expose the lower level class directly to the caller of the class.
another approach is to redistribute the functionality between the classes.
---
tags:
  - system-design
type: permanent
parent: "[[pass-through methods]]"
---

- They make classes shallower, they increase the interface complexity of the class. but they don't increase the total functionality of the system.
- pass-through methods also create dependencies between classes: if the signature of one layer changes other has to follow the update.

The **solution** is to refactor the classes so that each class has a distinct and coherent set of responsibilities.
one approach is to expose the lower level class directly to the caller of the class.
another approach is to redistribute the functionality between the classes.

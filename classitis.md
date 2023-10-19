---
tags:
  - software-design
related: "[[POSD - modules should be deep]]"
type:
  - literature
---
the conventional wisdom in programming is that classes should be small, not deep developer are often taught that the most important thing in class design is to break up larger classes into smaller ones the same advice is often given about methods "Any method longer than N lines should be divided into multiple methods" this approach results in large number of shallow classes and methods, which added to overall system complexity.

The extreme of the "classes should be small" approach is a syndrome I call classtis which stems from the mistaken view that "classes are good so more classes are better" In systems suffering from classitis, developers are encouraged to minimize the amount of functionality in each new class if you want more functionality introduce more classes.

Classitis may result in classes that are individually simple but it increases the complexity of the overall system.

small classes don't contribute much functionality so there have to be a lot of them, each with its own interface these interfaces accumulate to create tremendous complexity at the system level

small classes also result in a verbose programming style due to the boilerplate required for each class.


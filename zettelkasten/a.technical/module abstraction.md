---
tags:
  - software-design
  - book-notes
parent: "[[modules should be deep]]"
type: literature
deeper: "[[how module abstraction can go wrong]]"
---
**An abstraction is a simplified view of an entity, which omits unimportant details.**
Abstractions are useful because they make it easier for us to think about and manipulate complex things. In [[modular design]] each module provides an abstraction for its [[module interface]] the interface presents a simplified view of the module's functionality the details of the implementation are unimportant from the standpoint of the module's abstraction so they are omitted from the interface.
the word "**unimportant**" is crucial. the more unimportant details that are omitted from an abstraction the better however a detail can only be omitted from an abstraction if it is unimportant.


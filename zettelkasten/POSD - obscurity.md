---
tags:
  - book-notes
  - software-design
related: "[[POSD - causes of complexity]]"
type:
  - literature
aliases:
  - obscurity
---

## obscurity

- obscurity occurs when important information is not obvious. a simple example is a variable name that is so generic that it does not carry much useful information, so the only way to find out is to scan code for places where the variable is used.
- obscurity is often associated with dependencies where it is not obvious that a dependency exists
- inconsistency is also a major contributor to obscurity if the same variable name is used for two different purposes it won't be obvious to the developer which of these purposes a particular variable serves.
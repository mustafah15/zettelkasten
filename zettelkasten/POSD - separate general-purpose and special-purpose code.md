---
tags:
  - software-design
  - book-notes
parent: "[[POSD - better together or better apart]]"
type: reference
---
## separate general-purpose and special-purpose code
- if a module contains a mechanism that can be used for several different purposes, then it should provide just that one general-purpose mechanism. it should not include code that specializes the mechanism for a particular use, nor should it contain other general-purpose mechanisms special-purpose codes associated with a general-purpose should go normally in a different module.
- special-general-mix: when a general purpose mechanism also contains code specialized for a particular use of that mechanism this makes the mechanism more complicated and creates information leakage between the mechanism and the particular use case: future modifications to the use case are likely to require changes to the underlying mechanism as well.

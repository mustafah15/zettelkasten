---
tags:
  - book-notes
  - software-design
related: "[[POSD - different layer different abstraction]]"
type: reference
---
## When is interface duplication okay?
- having methods with the same signature is not always bad. the important thing is that each new method should contribute significant functionality. [[pass-through methods]] are bad because they contribute no new functionality.
-  An example of a useful method to call another method with the same signature is a [[dispatcher]]
- it's fine for several methods to have the same signature as long as each of them provides useful and distinct functionality.
- [[decorator design pattern|decorator design pattern]] is one that encourages API duplication across layers. A decorator object takes an existing object and extends its functionality it provides an API similar or identical to an underlying object.
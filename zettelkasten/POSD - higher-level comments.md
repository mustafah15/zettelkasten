---
tags:
  - book-notes
  - system-design
type:
  - literature
related: "[[POSD - how to write better comments]]"
---
a second way in which comments can argument the code by providing intuition. these comments are written at a higher level than the code itself; they omit the details and help the reader understand the code's overall intent and structure. this approach is commonly used for comments inside a method and for interface comments
```
// try to append the current key hash onto an existing 
// RPC to the desired server that hasn't been sent yet

```
- this comment does not contain any details instead, it describes the code's overall function at a higher level with high-level information, a reader can explain almost everything that happens in the code
- Higher-level comments are more difficult to write than lower-level comments because you must think about the code differently.
- ask yourself what is the code trying to do. what is the simplest thing you can say that explains everything in the code? and what is the most important thing about this code?
- Engineers tend to be very detail-oriented but, great software designers can also step back from the details and think about a system at a higher level. this means deciding which aspects of the system are most important and being able to ignore the low-level details and think about the system only in terms of its most fundamental characteristics which is the essence of abstraction finding a simple way to think about a complex entity and it's also what you must do when writing higher-level comments a good higher level comment expresses one or a few simple ideas that provide a conceptual framework.
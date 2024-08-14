---
tags:
  - book-notes
  - system-design
parent: "[[philosophy of software design]]"
type: reference
---
software systems are composed of layers, where higher layers use the facilities provided by lower layers. in a well-designed system, each layer provides a different abstraction from the layers above and below; if you follow a single operation as it moves up and down through the layer by invoking methods, the abstraction changes with each method call.
- for example: in a file system the uppermost layer implements a file abstraction. a file consists of a variable-length array of bytes, which can be updated by reading and writing variable-length byte ranges. the next lower layer in the file system implements a cache in memory of fixed-size disk blocks; callers assume that frequently used blocks will stay in memory where they can be accessed quickly, the lowest layer consists of device drivers that move blocks between secondary storage device and memory
if a system contains adjacent layers with similar abstractions, this is a red flag that suggests a problem with the class decomposition. This part discusses situations where this happens the problems that result, and how to refactor to eliminate the problems.

[[pass-through methods]]
[[pass-through variables]]

[[POSD - When is interface duplication okay?]]

---
tags:
  - software-design
  - book-notes
source: "[[modules should be deep]]"
type: literature
against: "[[shallow modules]]"
deeper: "[[module depth]]"
---
the best modules are those that provide powerful functionality yet have simple interfaces.
the best modules are deep they allow a lot of functionality to be accessed through a simple interface. [[shallow modules]] one with a relatively complex interface, but not much functionality.

a good example of a deep module is the garbage collector in a language such as Java or Go. this module has no interface at all; it works invisibly behind the scenes to reclaim unused memory. adding garbage collection to a system actually shrinks its overall interface since it eliminates the interface for freeing objects. the implementation is quite complex but that complexity is hidden from programmers using the language.


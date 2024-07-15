---
tags:
  - software-design
  - book-notes
related: "[[POSD - modules should be deep]]"
aliases:
  - deep modules
type: reference
---
the best modules are those that provide powerful functionality yet have simple interfaces.
the best modules are deep they allow a lot of functionality to be accessed through a simple interface. a [[shallow modules]] one with a relatively complex interface, but not much functionality.

module depth is a way of thinking about cost versus benefit. the benefit provided by a module is its functionality. the cost of a module(in terms of system complexity) is its interface. a module's interface represents the complexity that the module imposes on the rest of the system: the smaller and simpler the interface, the less complexity that it introduces. the best modules are those with the greatest benefit and the least cost.

a good example of a deep module is the garbage collector in a language such java or go. this module has no interface at all; it works invisibly behind the scenes to reclaim unused memory. adding garbage collection to a system actually shrinks its overall interface since it eliminates the interface for freeing objects. the implementation is quite complex but that complexity is hidden from programmers using the language.
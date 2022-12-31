---
title: deep modules
---

- Deep Modules
id:: f4b1cb25-9895-4cc9-9e31-238aa13c259e
	 - the best modules are those that provide powerful functionality yet have simple interfaces.
id:: 88b0054e-b2d5-4e85-bdf1-a69a45631f58

	 - the best modules are deep they allow a lot of functionality to be accessed through a simple interface. a [[shallow modules]] one with a relatively complex interface, but not much functionality.
id:: bdb9756a-331a-424a-993e-ee283169f11d

	 - module depth is a way of thinking about cost versus benefit. the benefit provided by a module is its functionality. the cost of a module(in terms of system complexity) is its interface. a module's interface represents the complexity that the module imposes on the rest of the system: the smaller and simpler the interface, the less complexity that it introduces. the best modules are those with the greatest benefit and the least cost.
id:: 037c557a-9deb-4f73-a10c-a9b4b845f357

	 - a good example of a deep module is the garbage collector in a language such java or go. this module has no interface at all; it works invisibly behind the scenes to reclaim unused memory. adding garbage collection to a system actually shrinks it's overall interface since it eliminates the interface for freeing objects. the implementation is quite complex but that complexity is hidden from programmers using the language. 
id:: 87e9d1ee-d907-4f0b-bddc-6e13ab03a13d

---
tags:
  - software-design
type: literature
parent: "[[why to write code comments]]"
---


### write code comments for better abstraction
- another reason for writing comments is abstractions, which include a lot of information that isn't obvious from the code. the idea of an abstraction is to provide a simple way of thinking about something but is so detailed that it can be hard to see the abstraction just from reading the code.
	- comments should provide a simpler higher-level view even if this information can be deduced by reading the code, we don't want to force users of a module to do that because reading the code is time-consuming and forces them to consider a lot of information that isn't needed to use the module.
	- A developer should be able to understand the abstraction provided by a module without reading any code other than its externally visible declarations. and to achieve this by supplementing the declarations with comments

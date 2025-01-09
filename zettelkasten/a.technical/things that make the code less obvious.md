---
tags:
  - software-design
parent: "[[your code can be more obvious]]"
---

many things can make code non obvious here's some examples
- Event-driven programming
	- in event-driven programming an application responds to external occurrences, such as the arrival of a network packet. one module is responsible for reporting incoming events other parts of the application register interest in certain events by asking the event module to invoke a given function or method when those events occur.
	- event-driven programming makes it hard to follow the flow of the control. the event handler functions are never invoked directly they are invoked indirectly by the event module. typically using a function pointer or interface, even if you find the point of invocation in the event module it still isn't possible to tell which specific function will be invoked this will depend on which handlers were registered at run time because this it's hard to reason about event-driven code or convince your self that it works to compensate for this obscurity use the [[interface comments]] for each handler function to indicate when it is invoked.
- Generic containers
	- Many Languages provide generic classes for grouping two or more items into a single object such as `Pair` in Java or `std:pair` in C++ these classes are tempting because they make it easy to pass around several objects with a single variable.
	- Unfortunately generic containers result in nonobvious code because the grouped elements have generic names that obscure their meaning.
	- There's one General Rule **Software should be designed for the ease of reading not the ease of writing.** Generic containers are expedient for the person writing the code but they create confusion for all the readers expedient for the person writing the code but they create confusion for all the readers that follow. it's better for the person writing the code to spend a few extra minutes defining a specific container structure so that the resulting code is more obvious.
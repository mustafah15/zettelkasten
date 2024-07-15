---
tags:
  - book-notes
  - software-design
parent: "[[philosophy of software design]]"
type: reference
---
[[POSD - obscurity|obscurity]] is one of the two main causes of complexity which occurs when important information about the system is not obvious to a new developer the solution to the obscurity problem is to write code in a way that makes it obvious.

If the code is obvious it means that someone can read the code quickly without much thought and their first guesses about the behavior or meaning of the code will be correct if the code is obvious a reader doesn't need to spend much time or effort to gather all information they need to work with the code.

If the code is not obvious then a reader must expend a lot of time and energy to understand it not only does this reduce their efficiency but it also increases the likelihood of misunderstanding and bugs obvious code needs fewer comments than nonobvious code.

Obvious is in the mind of the reader: it's easier to notice that someone else's code is nonobvious than to see problems with your own code. thus the best way to determine the obvious of code is through code reviews if someone reading your code says it's not obvious, then it's not obvious no matter how clear it may seem to you by trying to understand what made the code nonobovious you will learn how to write better code in the future.

### Things that can make the code more obvious

The two most important techniques for making code obvious are [[POSD - choosing names]] and [[POSD - consistency|code consistency]] but there are some other general-purpose techniques for making the code more obvious.
#### Judicious use of white space
the way code is formatted can impact how easy it is to understand. How you indent your code and put new empty lines can play a crucial role in making your code understandable. blank lines are also useful to separate major blocks of code within a method.

#### Comments
Sometimes it isn't possible to avoid code that is nonobvious. when this happens it is important to use comments to compensate by providing the missing information, to do that well you must put yourself in the position of the reader and figure out what is likely to confuse them, and what information will clear up that confusion.


### Things that make the code less obvious
many things can make code non obvious here's some examples
- Event-driven programming
	- in event-driven programming an application responds to external occurrences, such as the arrival of a network packet. one module is responsible for reporting incoming events other parts of the application register interest in certain events by asking the event module to invoke a given function or method when those events occur.
	- event-driven programming makes it hard to follow the flow of the control. the event handler functions are never invoked directly they are invoked indirectly by the event module. typically using a function pointer or interface, even if you find the point of invocation in the event module it still isn't possible to tell which specific function will be invoked this will depend on which handlers were registered at run time because this it's hard to reason about event-driven code or convince your self that it works to compensate for this obscurity use the [[POSD - interface comments]] for each handler function to indicate when it is invoked.
- Generic containers
	- Many Languages provide generic classes for grouping two or more items into a single object such as `Pair` in Java or `std:pair` in C++ these classes are tempting because they make it easy to pass around several objects with a single variable.
	- Unfortunately generic containers result in nonobvious code because the grouped elements have generic names that obscure their meaning.
	- There's one General Rule **Software should be designed for the ease of reading not the ease of writing.** Generic containers are expedient for the person writing the code but they create confusion for all the readers expedient for the person writing the code but they create confusion for all the readers that follow. it's better for the person writing the code to spend a few extra minutes defining a specific container structure so that the resulting code is more obvious.
	- 
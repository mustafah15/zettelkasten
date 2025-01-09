---
tags:
  - software-design
parent: "[[module abstraction]]"
---

An abstraction can go wrong in two ways.
- First, it can include details that are not really important; when this happens it makes the abstraction more complicated than necessary, which increases the [[cognitive load]] on developers using the abstraction.
- The second error is when an abstraction omits details that are really important. This results in obscurity developers looking only at the abstraction will not have all the information they need to use the abstraction correctly. An abstraction that omits important details is a false abstraction it might appear simple, but in reality, it isn't.


The key to designing abstraction is to understand what is important and to look for designs that minimize the amount of information that is important.

We depend on abstractions to manage complexity not just in programming but pervasively in our everyday lives. Cars provide simple abstractions that allow us to drive them without understanding the mechanisms for the endless tons of electronic stuff that is already inside.
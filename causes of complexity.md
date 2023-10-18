---
tags:
  - software-design
type:
  - literature
related: "[[POSD - complexity in software design]]"
---
The next step is to understand what causes complexity in the first place so that we can design systems to avoid the problems.
complexity is caused by two main things

- dependencies
	- a dependency exists when a given piece of code can not be understood and modified in isolation the code relates in some way to another code, and the other code must be considered modified if the given code is changed.
	- dependencies are a fundamental part of software and can't be completely eliminated in fact we intentionally introduce dependencies as part of the software design process every time you write a new class you create dependencies around the API for that class however one of the goals of software design is to reduce the number of dependencies and to make the dependencies that remain as simple and obvious as possible.
- obscurity
	- obscurity occurs when important information is not obvious. a simple example is a variable name that is so generic that it does not carry much useful information, so the only way to find out is to scan code for places where the variable is used.
	- obscurity is often associated with dependencies where it is not obvious that a dependency exists
	- inconsistency is also a major contributor to obscurity if the same variable name is used for two different purposes it won't be obvious to the developer which of these purposes a particular variable serves.
- 
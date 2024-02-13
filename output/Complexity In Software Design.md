---
tags:
  - writing
  - software-design
related: "[[POSD - complexity in software design]]"
type:
  - permanent
dg-publish: true
---

Have you ever tried to change a small simple piece of code and ended up crashing the whole application, or introducing new bugs? personally, I have faced such situations many times before the codebase I was trying to fix or to change was too complex to fix or to add new simple features to it. 

Have you thought about why this codebase is complex and what are the symptoms and causes of complexity? during this post, let's discuss complexity symptoms, how complexity builds up into your code base, and how it's possible to fight against complexity.

Let's start with a definition, what is the complexity? complexity is anything related to the structure of a software system that makes it hard to understand and modify the system.
Also, it's important to understand that complexity can take many forms for example it might be hard to understand how a new piece of code works, and it might take a lot of work to implement even small improvements. In a simple system, larger improvements should be implemented with less effort. 

### Complexity Symptoms
- Change Amplification
	The first symptom of complexity is that a seemingly simple change requires code modification in many different places, so one of the goals of a good design is to reduce the amount of code that is affected by each design decision, so design changes don't require very many code changes.
- Cognitive Load
	Cognitive load means how much a developer needs to know in order to complete a task. A higher cognitive load means that developers have to spend more time learning the required information and there is a greater risk of bugs because they have missed something important. cognitive load arises in many forms such as APIs with many methods, inconsistencies, and dependencies between modules.
- Unknown Unknowns
	The third symptom of complexity is that it's not obvious which piece of code should be modified to complete a task, or what information a developer must have to carry out the task successfully. Of the three manifestations of complexity, unknown unknowns are the worst. an unknown unknowns means that there is something you need to know but there's no way for you to find out what it is, or even whether there is an issue or not. you won't find out about it until bugs appear after you make a change.
### Complexity Causality 
Complexity is not caused by a single catastrophic error however it accumulates in lots of small chunks a new single dependency or obscure piece of code by itself is unlikely to affect significantly the maintainability of a software system. complexity comes because hundreds or thousands of small dependencies and obscurities build up over time. This incremental nature of complexity makes it hard to control it's easy to convince yourself that a little bit of complexity introduced by your current change is not a big deal however if every developer takes this approach for every change complexity accumulates rapidly.
There are two main ways that complexity can be introduced into your codebase:
- Dependencies
	 A dependency exists when a given piece of code can not be understood and modified in isolation, the code relates in some way to another code. Dependencies are a fundamental part of software and can't be completely eliminated in fact we intentionally introduce dependencies as part of the software design process every time you write a new class you create dependencies around the API for that class however one of the goals of software design is to reduce the number of dependencies and to make the dependencies that remain as simple and obvious as possible.
- Obscurity
	obscurity occurs when important information is not obvious. a simple example is a variable name that is so generic that it does not carry much useful information, so the only way to find out is to scan code for places where the variable is used. Inconsistency is a major contributor to obscurity if the same variable name is used for two different purposes it won't be obvious to the developer which of these purposes a particular variable serves.

### Fighting against complexity 
- eliminate complexity by making code simpler and more obvious, for example, complexity can be reduced by eliminating special cases or using identifiers in a function. 
- encapsulate complexity, programmers can work on a system without being exposed to all of its complexity at once by embracing  *modular design*

Finally, complexity can sneak into every codebase and it's important to know what complexity symptoms, causes, and how to fight against it in every technical decision you take during your day-to-day work to prevent complex code from building up incrementally.

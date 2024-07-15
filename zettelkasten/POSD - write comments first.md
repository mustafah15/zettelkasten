---
tags:
  - book-notes
  - software-design
aliases:
  - write comments first
parent: "[[philosophy of software design]]"
type: reference
---
one of the surest ways to produce poor-quality documentation is to write documentation at the end of the development process. writing the comments first makes documentation part of the design process, not only does this produce better documentation but it also produces better designs and it makes the process of writing documentation more enjoyable.
### A different way to write comments
- I used a different approach to writing comments, where I wrote the comments at the very beginning:
	- for a new class start by writing the class [[POSD - interface comments]]
	- next, write interface comments and signatures for the most important public methods but leave the method bodies empty.
	- Iterate a bit over these comments until the basic structure feels about right.
	- at this point write declaration and comments for the most important class instance variables in the class.
	- finally fill in the bodies of the methods, adding implementation comments as needed.
	- while writing method bodies you might discover the need for additional methods and instance variables. for each new method write the interface comment before the body of the method; for instance, variables fill in the comment at the same time that I write the variable declaration.
- when the code is done the comments are also done there is never a backlog of unwritten comments.

### the comments-first approach has three benefits.

- first, it produces better comments if you write the comments as you are designing the class, the key design issues will be fresh in your mind, so it's easy to record the. it's better to write the interface comment for each method before its body so you can focus on the method abstraction and interface without being distracted by its implementation.
- the second and most important benefit is that it improves the system design. comments provide the only way to fully capture abstractions. and good abstraction is fundamental to good system design so if you write comments describing the abstractions at the beginning, you can review and tune them before writing implementation code. to write a good comment you must identify the essence of a variable or piece of code what is the most important aspect of this thing? is it important to do this early in the design process; otherwise you are just hacking the code.
	- comments can serve as a canary in the coal mine of complexity if a method or variable requires a long comment it is a red flag that you don't have a good abstraction. as the best way to judge the complexity of an interface is from the comments that describe it. if the interface comment for a method provides all the information needed to use the method and is also short and simple, that indicates that the method has a simple interface.
	- Hard to describe
		- conversely, if there's no way to describe a method completely without a long and complicated comment with the implementation to get a sense of how deep the method is; the interface comment must describe all the major features of the implementation. then the method is shallow #[[software design red flags]] as the comment describing a method or variable should be simple yet complete.
- the third and final benefit of writing comments early is that it makes comment-writing more fun. One of the most enjoyable parts of programming is the early design phase for a new class, where you flesh out the abstractions and structure for the class. most of your comments are written during this phase, and the comments are how you record and test the quality of your design decisions.

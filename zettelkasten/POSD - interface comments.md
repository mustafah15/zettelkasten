---
tags:
  - book-notes
  - software-design
related: "[[POSD - how to write better comments]]"
type:
  - literature
---
- one of the most important roles for comments is to define abstraction, code is not suitable for describing abstractions; it's too low level and it includes implementation details that shouldn't be visible in the abstraction
- the only way to describe an abstraction in with comments if you want code that presents good abstractions you must document those abstractions with comments.
- the first step in documenting abstractions is to separate interface comments from implementation

- interface comments provide information that someone needs to know in order to use a class or method; they define the abstraction.
- implementation comments describe how a class or method works internally in order to implement the abstraction.

- it's important to separate these two kinds of comments so that users of an interface are not exposed to implementation details. if interface comments must also describe the implementation, the module is [[shallow modules]] this means that the act of writing comments can provide clues about the quality of the design.
- the interface comments for a class provide a high-level description of the abstraction provided by the class, such as the following
```c++
/**
* This class implements a simple server-side interface to the HTTP
* protocol: by using this class, an application can receive HTTP
* requests, process them, and return responses, Each instance of this
* class corresponds to a particular socket used to receive
* requests. The current implementation is single-threaded and
* process one request at a time
*/

class Http {}
```
This comment describes the overall capabilities of the class, without any implementation details or even the specifics of a particular method, it also describes what each instance of the class represents. finally, the comments describe the limitations of the class which may be important to developers contemplating whether to use it.

the interface comment for a method includes both higher-level information for abstraction and lower-level details for precision as:
- the comment usually starts with a sentence or two describing the behavior of the method as perceived by the caller this is the higher-level abstraction.
- the comment must describe each argument and the return value if any, these comments must be very precise and must describe any constrains on argument values as well as dependencies between arguments.
- if the method has any side effects these must be documented in the interface comment
- a method's interface comment must describe any exceptions that can be emanate from the method.
- If there are any preconditions that must be satisfied before a method is invoked, these must be described.
- 
- Implementation Documentation contaminates the interface
	- this red flag occurs when interface documentation describes implementation details that aren't needed in order to use the thing being documented #[[software design red flags]]
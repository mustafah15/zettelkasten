---
tags:
  - book-notes
  - software-design
parent: "[[philosophy of software design]]"
type: reference
---
## why exceptions add complexity
- the author uses the term exception to refer to any uncommon condition that alters the normal flow of control in a program. many programming languages include a formal exception mechanism that allows exceptions to be thrown by lower-level code and caught by enclosing code. however, exceptions can happen without using a formal exception reporting mechanism, such as when a method returns a special value indicating that it didn't complete its normal behavior. All of these forms of exceptions contribute to complexity.
- **Exceptions Reasons** - A piece of code may encounter exceptions in several different ways:
	- A caller may provide an argument or config information.
	- An invoked method may not be able to complete a requested operation.
	- network packets may be lost or delayed, servers may not respond in a timely fashion.
	- the code may detect bugs internal inconsistencies or situations it is not prepared to handle.

- when an exception occurs, the programmer can deal with it in two ways each of which can be complicated.
	- the first approach is to move forward and complete the work in progress despite the exceptions.
		- if a network packet is lost it can be resent if data is corrupted, perhaps it can be recovered from a redundant copy as perhaps the packet wasn't actually lost but was simply delayed.
	- the second approach is to abort the operation in progress and report the exception upwards
	- however aborting can be complicated because the exception may have occurred at a point where system state is inconsistent the exception handling code must restore consistency, such as by unwinding any changes made before the exception occurred.

- Exception handling code creates opportunities for more exceptions and to prevent an unending cascade of exceptions the developer must eventually find a way to handle exceptions without introducing more exceptions.
- Most programmers are taught that it's important to detect any report errors they often interpret this to mean "the more errors detected, the better." which might lead to an over-defensive style where anything that looks even a bit suspicious is that increases the complexity of the system.
- It's tempting to use exceptions to avoid dealing with difficult situations rather than figuring out a clean way to handle it, just throw an exception and punt the problem to the caller.
	- some might argue that this approach empowers callers since it allows each to figure out what to do for the particular situation, there's a good chance that the caller won't know what to do either.
	- generating an exception in a situation like this just passes the problem to someone else and adds to the system's complexity

- Exceptions thrown by a class are part of its interface; classes with lots of exceptions have a complex interface they are shallower than classes with fewer exceptions. [[shallow modules]]
- An Exception is a particularly complex element of an interface. why? because it can propagate up through several stack levels before being caught so it affects not just the method's caller but potentially also higher-level callers thus the complexity of an exception comes from the exception handling code.
- the best way to reduce complexity damage caused by exception handling is to reduce the number of places where exceptions have to be handled
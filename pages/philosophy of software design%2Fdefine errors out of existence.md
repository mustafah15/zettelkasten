- Exception handling is one of the worst sources of complexity in software systems because code that deals with special conditions is inherently harder to write than code that deals with normal cases. and developer often define exceptions without considering how they will be handled.
- why exceptions add complexity
  collapsed:: true
	- the author uses term exception to refer to any un common condition that alter the normal flow of control in a program. many programming languages include a formal exception mechanism that allows exceptions to be thrown by lower level code and caught by enclosing code. however exceptions can happen without using a formal exception reporting mechanism, such as when a method returns a special value indicating that it didn't complete its normal behaviour. All of these forms of exceptions contribute to complexity.
	- **Exceptions Reasons** - A piece of code may encounter exceptions in several different ways:
		- A caller may provide a argument or config information.
		- An invoked method may not be able to complete a requested operation.
		- network packets may be list or delayed, servers may not respond in a timely fashion.
		- the code may detect bugs internal inconsistencies or situations it is not prepared to handle.
	- when an exception occurs, the programmer can deal with it in two ways each of which can be complicated.
		- the first approach is to move forward and complete the work in progress in spite of the exception.
			- if a network packet lost it can be resent if data is corrupted, perhaps it can be recovered from a redundant copy as perhaps the packet wasn't actually lost but was simply delayed.
		- the second approach is to abort the operation in progress and report the exception upwards
			- however aborting can be complicated because the exception may have occurred at a point where system state is inconsistent the exception handling code must restore consistency, such as by unwinding any changes made before the exception occurred.
	- Exception handling code creates opportunities for more exceptions and to prevent an unending cascade of exceptions the developer must eventually find a way to handle exceptions without introducing more exceptions.
	- Most programmers are taught that it's important to detect any report errors they often interpret this to mean "the more errors detected, the better." which might lead to an over defensive style where anything that looks even a bit suspicious is that increase the complexity of the system.
	- It's tempting to use exceptions to avoid dealing with difficult situations rather than figuring out a clean way to handle it, just throw an exception and punt the problem to the caller.
		- some might argue that this approach empowers callers, since it allows each figuring out what to do for the particular situation, there's a good chance that the caller won't know what to do either.
		- generating an exception in a situation like this just passes the problem to someone else and adds to the system complexity
	- Exceptions thrown by a class are part of its interface; classes with lots of exceptions have a complex interface they are shallower than classes with fewer exceptions. [[shallow modules]]
	- An Exception is a particularly complex element of an interface. why? because it can propagate up through several stack levels before being caught so it affects not just the method's caller but potentially also higher-level callers thus the complexity of an exception comes from the exception handling code.
	- the best way to reduce complexity damage caused by exception handling is to reduce the number of places where exceptions have to be handled
- FOUR TECHNIQUES FOR REDUCING THE NUMBER OF EXCEPTION HANDLERS
  collapsed:: true
	- define errors out of existence
		- the best way to eliminate exception handling complexity is to define your APIs so that there are no exceptions to handle: define errors out of existence. this may seem sinful, but it is very effective in practice. consider TCL `uset` command instead of throwing error when unset asked to delete an unknown variable, it should have simply returned without doing anything.
		- with the first definition, unset can't do its job if the variable doesn't exist so generating an exception makes sense. with the second definition, it is perfectly natural for `unset` to be invoked with the name of a variable that doesn't exist. in this case it's work is already done, so it can simply return there is no longer an error case to report.
	- mask exceptions
		- [[exception masking]]
	- exception aggregation
		- [[exception aggregation]]
	- just crash?
		- The fourth technique for reducing complexity related to exception handling is to crash the application. in the most applications there will be certain errors that it's not worth trying to handle it. typically these errors are difficult or impossible to handle and don't occur very often. the simplest thing to do in response to these errors is to print diagnostic information and then abort the application. one example is "out of memory" errors that occur during storage allocation.
		- As There's not much an application can do when it discovers that memory is exhausted. in principle the application could look for unneeded memory to free but if the application had unneeded memory it could already have freed it which would have prevented the out-of-memory error in the first place.
		- There are many other examples of errors where crashing the application makes sense. for most programs if an io error occurs while reading or writing an open file or if a network socket cannot be opened, there's not much the application can do to recover so aborting with a clear error message is a sensible approach. These errors are infrequent so they are unlikely to affect the overall usability of the application. Aborting with an error message is also appropriate if an application encounters an internal error such as an inconsistent data structure. conditions like this probably indicate bugs in the program.
	-
- Taking it too far
	- Defining away exceptions, or masking them inside a module only makes sense if the exception information isn't needed outside the module this was true for the examples we had before.
	- However it is possible to take this idea too far. in a module for network communication if you masked all network exceptions if a network error occurred, your module will catch it, discard it and continued as if there were no problem. this means the applications using the module had no way to find out if messages were lost or a peer server failed; without this information it is impossible to build robust application in this case it is essential for the module to expose the exceptions even though they add complexity to the module's interface with exceptions as with many other areas in software design you must determine what is important and what is not important things that are not important should be hidden and the more of the better but when something is important it must be exposed
---
title: javascript interviews questions
---

- what is the difference between var, const, let?
	 - **var** defines variables in global scope so we should never use var.

	 - **const** defines variables in the local scope but once it's values is assigned we can't change it.

	 - **let** defines variables in the local scope also but we can reassign the value of the variable.

- how js handle async tasks? explain eventloop?
	 - In nodejs slow I/O operations are handled with events and callbacks so that they don't block the main single threaded execution runtime. when talking about Node's architecture the term I/O is usually used to reference accessing disk and network resources, we can handle requests for these slow operations in one of many ways.

	 - **synchronous**
		 - it's easiest way to go with it but it's horrible because one request is going to holdup other requests.

	 - async with **event loop**
		 - it's the entity that handles external events and convert them into callback invocations.

		 - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2FLwSIBIo9m6.png?alt=media&token=5cced22b-665e-43ed-91ff-48c3e3e7e8e8)

		 - **call stack**
			 - In js code every time we step into a function we push into stack and every time we return from a function it gets popped out of the stack.

		 - **event queue**
			 - the call back queue it's basically a list of things to be processed.

		 - **Node or browser engine**
			 - it execute the slow operations like setting timer for settimeout function and fire an event when it done  so it's call back can be moved to the event queue.

		 - ♻️ When the call stack gets empty: while the queue is not empty, it dequeue an event (a callback) from the event queue to the call stack to get executed.

- what is the difference between `()=> {}` arrow functions and normal js functions?
	 - `this` value inside a regular function is dynamic and depends on the invocation. But this inside the arrow function is bound lexically and equals to this of the outer scope.

- what is the difference between `==` and `===`
	 - Strict Equality `===` compares two values for equality. Neither value is implicitly converted to some other value before being compared. If the values have different types, the values are considered unequal. If the values have the same type, are not numbers, and have the same value, they're considered equal. Finally, if both values are numbers, they're considered equal if they're both not NaN and are the same value, or if one is +0 and one is -0.

	 - Loose Equality `==` 
		 - Loose equality compares two values for equality __after__ converting both values to a common type. After conversions (one or both sides may undergo conversions), the final equality comparison is performed exactly as === performs it.

		 - Loose equality is __symmetric__: A == B always has identical semantics to B == A for any values of A and B (except for the order of applied conversions).

		 - undefined and null are loosely equal; that is, undefined == null is true, and null == undefined is true

- what is the scope in js 
	 - __Scope__ in JavaScript refers to the current context of code, which determines the accessibility of variables to JavaScript. The two types of scope are __local__ and __global__:
		 - **Global variables** are those declared outside of a block

		 - **Local variables** are those declared inside of a block

- what is hoisting 
	 - If we attempt to use a variable before it has been declared and initialized, it will return undefined. that is hoisting. but we can avoid it if we use `let` and `const` because you can't use variables defined with let and const we cannot access them before the actual declaration is evaluated at runtime. 

- What are callbacks?
	 - A callback is a function that will be executed after another async function gets executed.

- what is the callback hell?
	 - is the long nesting of async callback functions, you can avoid them if we use async & await or promises.

- what is promises and what is the promise chain.
	 - a promise is a syntax suger to avoid callbacks in JS a promise has 3 states
		 - pending: a promise is not resolved or rejected and still in the initial state.

		 - fulfilled: meaning that the operation was completed successfully.

		 - __rejected__: meaning that the operation failed, and it throws an error that can be handled in the `.catch()` block

	 - a promise chain is you have a long chain of `.then()` and all them depends on the pervious promise, that can lead to a long chain of `.then()` code block.

	 - 
```javascript
myPromise
.then(handleResolvedA)
.then(handleResolvedB)
.then(handleResolvedC)
.catch(handleRejectedAny);
```

- how to handle a set of async calls or actions 
	 - you can use `Promise.all([])` which accept array of promises and we can wait until all the promises inside get resolved

- 

- [Must-know JavaScript Features](https://www.youtube.com/playlist?list=PL0zVEGEvSaeHJppaRLrqjeTPnCH6vw-sm)

- [recommended reads](https://medium.com/javascript-scene/composing-software-the-book-f31c77fc3ddc)

- [videos](https://www.youtube.com/watch?v=GhbhD1HR5vk&list=PL0zVEGEvSaeHBZFy6Q8731rcwk0Gtuxub)

---
title: State
---

- what is the state pattern 
id:: 4ae9191d-09bd-4ed8-b034-3e799a176437
	 - The main idea is that, at any given moment, there’s a __finite__ number of __states__ which a program can be in. Within any unique state, the program behaves differently, and the program can be switched from one state to another instantaneously. However, depending on the current state, the program may or may not switch to certain other states. These switching rules, called __transitions__, are also finite and predetermined.

	 - You can also apply this approach to objects. Imagine that we have a Document class. A document can be in one of three states: Draft, Moderation and Published. The publish method of the document works a little bit differently in each state:
		 - In Draft, it moves the document to moderation.

		 - In Moderation, it makes the document public, but only if the current user is an administrator.

		 - In Published, it doesn’t do anything at all.

	 - In plain words
id:: f6329bce-7059-42ef-a7da-68c8f8df4a0b
		 - It lets you change the behavior of a class when the state changes.
id:: 01b7c4f9-e357-4d15-ab4c-fbab859efd77

	 - Wikipedia says
id:: 9b7030b2-7805-4617-9e3d-8c8e257e72c7
		 - The state pattern is a behavioural software design pattern that implements a state machine in an object-oriented way. With the state pattern, a state machine is implemented by implementing each individual state as a derived class of the state pattern interface and implementing state transitions by invoking methods defined by the pattern's superclass. The state pattern can be interpreted as a strategy pattern that is able to switch the current strategy through invocations of methods defined in the pattern's interface.
id:: 5e0149b6-c3c6-4fdf-a6a7-e89f62062b94

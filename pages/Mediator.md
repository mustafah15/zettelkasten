---
title: Mediator
---

- What is the mediator pattern?
id:: f0633cb1-dd09-4ec8-8789-dfb5c58a8ec8
	 - It is a behavioural pattern that allows a **mediator** (__a central authority__) to act as the coordinator between different objects, instead of the objects referring to each other directly. A __mediator__ as the name implies, is a central authority through which various components can communicate. It allows the loose coupling of objects.
id:: be11ce29-879b-4d4c-a57a-8b23eaf68ef7

	 - A real-life example is a __chat application__. Here, the chat box acts as the __mediator__ through which various users interact with one another.
id:: 43585fa8-aa3a-4463-9cfb-4c8460a0d12e

	 - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2FgTAiY4omKP.png?alt=media&token=41a468e0-9fa9-4059-a537-1dc3d213af24)
id:: e922a0ab-90d2-4dfc-b1c1-a476ce03bbd8

	 - In plain words
id:: a41a2c0a-c4da-47d0-a68b-eada11f10dc1
		 - The mediator pattern adds a third party object (called the mediator) to control the interaction between two objects (called colleagues). It helps reduce the coupling between the classes communicating with each other. Because now they don't need to have the knowledge of each other's implementation.
id:: 1cc730b1-9d3f-435b-b5c0-231a9962c89f

	 - Wikipedia says
id:: e078d2d4-7f04-46c4-a700-b4f520b14d65
		 - In software engineering, the mediator pattern defines an object that encapsulates how a set of objects interact. This pattern is considered to be a behavioural pattern due to the way it can alter the program's running behaviour.
id:: 0160ab68-b118-4501-aab7-5040c7a2c101

	 - When to use the mediator pattern?
id:: 3ae9dc99-fcc0-467c-b799-1efcb4bcde5f
		 - If your system has multiple parts that need to communicate
id:: 49e02fd5-96bb-463a-9e39-547d94edad13

		 - To avoid tight coupling of objects in a system with a lot of objects
id:: c51917aa-7e00-4c42-be79-bd5d02da0270

		 - To improve code readability
id:: 0b80b8a0-f805-4bf3-b087-7638a1d211e0

		 - To make code easier to maintain
id:: bc4dfe70-d556-45c7-97ec-a35df23a5542

		 - If communication between objects becomes complex and hinders the reusability of code
id:: fbcaadff-b117-45a6-8bf8-56f9d6fd4a5d

---
title: Chain of Responsibility
---

- What is the chain of responsibility pattern?
id:: 76fe258e-ebbe-4908-a44e-1a19e6d266a7
	 - The **chain of responsibility** pattern allows a request sent by a client to be received by more than one object. It creates a chain of loosely-coupled objects that, upon receiving the request, either handle it or pass it to the next handler object.
id:: cc6a9274-0513-4ea9-a069-3f693b8d7cea

	 - A common example of this pattern is __event bubbling__ in [DOM](https://www.educative.io/edpresso/what-is-dom). An event propagates through different nested elements of the DOM until one of them handles it.
id:: e87ebdbe-ada1-4da0-8ecd-aa6d2c19c868

	 - In plain words:
id:: 53fed707-e89f-4d6e-9f92-6ced1d200bdd
		 - It helps building a chain of objects. Request enters from one end and keeps going from object to object till it finds the suitable handler.
id:: 03a02c79-9bab-4cc2-87c7-7a05f371696e

	 - Wikipedia says:
id:: 83065a00-14fe-4061-b7c4-9d6eeeb32481
		 - In object-oriented design, the chain-of-responsibility pattern is a design pattern consisting of a source of command objects and a series of processing objects. Each processing object contains logic that defines the types of command objects that it can handle; the rest are passed to the next processing object in the chain.
id:: 1a47c339-6b0b-4a97-9121-5b6569fc768e

	 - When to use the chain of responsibility pattern?
id:: f018ec74-7b12-43fd-a886-ca191f8788ed
		 - You can use it if your program is written to handle various requests in different ways without knowing the sequence and type of requests beforehand. It allows you to chain several handlers, thus, allowing all of them a chance to process the request.
id:: 5653d0f3-7d03-458b-b51b-38fb733f0bfe

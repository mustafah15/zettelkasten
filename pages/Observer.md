---
title: Observer
---

- What is the observer pattern?
id:: 96fb1e7b-cda1-47da-ba01-928cfc570e57
	 - The __observer pattern__ is a major behavioral design pattern. It allows objects (__observers__) that have subscribed to an event to wait for input and react to it when notified. This means they don’t have to continuously keep checking whether the input has been provided or not. The __main subject__ maintains a list of all the observers and whenever the event occurs, it notifies the observers so they can update their states accordingly.
id:: e96e92c3-cba4-4055-8a58-f231f18adb55

	 - Let’s look at a real-life example that we can map to this pattern. Consider a website that posts interesting articles. Every day, you visit the site to check for new articles and if there is none, you revisit after some time/days. What if you get a subscription to the website instead? Once you have the subscription, you’ll get notified every time a new article is posted. So now, instead of checking the site every few hours, you just wait for the notification about a new article.
id:: e490d8e8-d73d-4cd5-aaf0-e37eeb8685b5

	 - In plain words
id:: 974161e2-46e5-4778-9731-3d747601afdc
		 - Defines a dependency between objects so that whenever an object changes its state, all its dependents are notified.
id:: 04a19000-642d-48af-9869-1a44282ce68b

	 - Wikipedia says
id:: 93e170e5-774a-4d03-b767-6ecf50adc1da
		 - The observer pattern is a software design pattern in which an object, called the subject, maintains a list of its dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their methods.
id:: 44106412-c2ff-4e25-a0fe-16f8c4d8fa26

	 - When to use the observer pattern?
id:: db66fb49-49f1-4aed-847a-dab6a27037e2
		 - To improve code management by breaking down large applications into a system of loosely-coupled objects
id:: 45b5705e-f07b-46b0-9570-79907f153e7a

		 - provide greater flexibility by enabling a dynamic relationship between observers and subscribers which is otherwise not possible due to tight coupling
id:: d2c0fd98-4735-435d-ba76-de5bd6f76a0d

		 - improve communication between different parts of the application
id:: d3ef64d5-aa0d-45ef-b8af-12f7b2fc559e

		 - create a one-to-many dependency between objects that are loosely coupled
id:: ebde1594-f626-4f5a-ab12-c498cf695792

---
title: classitis
---

- Classitis
id:: b6652e07-d9d9-427c-8f7f-76d5d5baa41b
	 - the conventional wisdom in programming is that classes should be small not deep developer are often taught that the most important thing in class design is to break up larger classes into smaller ones the same advice is often given about methods "any method longer than N lines should be divided into multiple methods" this approach results in large number of shallow classes and methods, which added to overall system complexity. 
id:: 3d5d51c0-2991-4d1d-8341-26e90a493fd9

	 - the extreme of the "classes should be small" approach is a syndrome I call classtis which stem from the mistaken view that "classes are good so more classes are better" in systems suffering from classitis, developers  are encouraged to minimize the amount of functionality in each new class if you want more functionality introduce more classes.
id:: 2bc1eff9-c49a-415a-8df3-2859a9d21ebe

	 - Classitis may result in classes that are are individually simple but it increases the complexity of the overall system. 
id:: 0b96d9e5-ade2-415a-bf72-d4d8258bb3fb
		 - small classes don't contribute much functionality so there have to be a lot of them, each with its own interface these interfaces accumulate to create tremendous complexity at the system level 
id:: 49d40838-686d-465f-96d3-03e7ed92c534

		 - small classes also result in a verbose programming style due to the boilerplate required for each class.
id:: e8937a51-aa56-4e56-bd0a-64398de30aff

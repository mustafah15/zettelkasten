---
title: symptoms of complexity
---

- symptoms of complexity
id:: 932e6aec-8905-40ef-9ffc-c1e46d1ea4c9
	 - [[change amplification]]
id:: b453841a-faeb-4f9d-850b-88b39358b0a7
		 - the first symptom of complexity is that a seemingly simple change requires code modifications in many different places. so one of the goals of good design is to reduce the amount of code that is affected by each design decision, so design changes don't require very many code modifications.
id:: 35c166ad-8c17-4fd6-928c-03839c36ba82

	 - [[cognitive load]]
id:: 4be21345-af6f-4c9e-aedd-878aaacc5eb2
		 - cognitive load means how much a developer needs to know in order to complete a task. A higher cognitive load means that developers have to spend more time learning the required information and there is a greater risk of bugs because they have missed something important. cognitive load arises in many forms such as APIs with many methods, global variables inconsistencies and dependencies between modules.
id:: 6ba366d2-a2c0-48de-8423-ccb2ba05cb52

		 - system designers sometimes assume a wrong assumption that complexity can be measured by lines of code. they assume that if one implementation is shorter than another, then it must be simpler; if it only takes a few lines of code to make a change, then the change must be easy however this view ignores the costs associated with cognitive load I have seen frameworks that allowed applications to be written with only a few lines of code but it was extremely difficult to figure out what those lines where. 
id:: f93c84b7-2e97-443f-a97f-c77f3cd1214c

		 - **sometimes an approach that requires more lines of code actually simpler because it reduces cognitive load**
id:: e7307ede-2fd1-4748-bc11-c77a198d46b8

	 - [[unknown unknowns]]
id:: 27085202-6c61-4fb2-8598-9c9d38de228b
		 - the third symptom of complexity is that it is not obvious which pieces of code should be modified to complete a task, or what information a developer musth have to carry out the task successfully. of the three manifestations complexity unknown unknowns are the worst. an unknown unknown means that there is something you need to know but there's no way for you to find out whit it is, or even whether there is an issue or not. you won't find about it until bugs appear after you make a change. 
id:: 1318cd47-7182-405f-8f79-10ffc0474298

		 - changes amplification is annoying but as long it is clear which code needs to be modified. the system will work once the change has been completed. similarly, a high cognitive load will increase the cost of a change but if it is clear which information to read, the change is sitll likely to be correct. with unknown unknowns it's unclear what to do or wether a proposed system which is impossible for system for any size. even this may not be suffcient, because a change may depend on a subtle design decision that was never documented. 
id:: c8c0511d-3448-4655-9753-bb693750d106

		 - One of the most important goals of a good design is for a system to be obvious. this is the opposite of high cognitive load and unknown unknowns. in obvious system a developer can quickly understand how existing code works and what is required to about what to do.
id:: d3ab3028-cf10-4e27-bfcb-f726485e49fb

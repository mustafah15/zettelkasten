---
title: Bridge pattern
---

- what is the bridge pattern 
id:: efdabaea-8b8f-4672-acf0-bea2cab166bc
	 - The bridge pattern allows separate components with separate interfaces to work together. It keeps an object’s interface separate from its implementation, allowing the two to vary independently.
id:: e4e098a0-d3d1-4c88-a4fc-1f991c60728b

	 - An example is controlling an air conditioner with a remote. The air conditioners can be of different types and each of them is controlled by a different remote. The remotes can vary, that is, a new one with better features can be introduced, but that won’t make any changes to the air conditioner classes. The same goes the other way round. The bridge pattern allows input and output devices to work together but vary independently.
id:: 07903a34-b038-45af-8f77-cab9035b255f

	 - In Plain Words
id:: dbb792c1-99b0-4109-9b44-668c7d4d60c9
		 - The bridge pattern is about preferring composition over inheritance. Implementation details are pushed from a hierarchy to another object with a separate hierarchy.
id:: 2ed73d5a-b26d-46c0-ae7b-f6f74fab8f1c

	 - Wikipedia says
id:: f00ee2b2-8a47-45fe-9409-0f97404cca76
		 - The bridge pattern is a design pattern used in software engineering that is meant to "decouple an abstraction from its implementation so that the two can vary independently"
id:: 1e338ffe-aeed-4647-8122-07e4a614f64e

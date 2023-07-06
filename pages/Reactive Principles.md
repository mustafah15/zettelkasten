---
title: Reactive Principles
---

- The Reactive Architecture Principles 
  id:: b1556694-4865-4544-9275-869cc0e58b57
	- ![](https://www.researchgate.net/profile/David-Bauer-7/publication/326960759/figure/fig1/AS:658175791472640@1533932745053/Presentation-of-the-basic-principles-of-reactive-systems-from-the-Reactive-Manifesto.png)
	  id:: 11ccdef5-0485-452a-8b38-b2200286f794
	- **Responsive**: A Reactive system consistently responds in a timely fashion.
	  id:: 704094f6-1b6c-47c1-9f3e-6325303e64d8
		- Responsiveness is the cornerstone of system usability, so the reactive systems must be fast to detect problems when they begin to arise.
		  id:: 3996acda-87f7-4acb-aacd-4fad90612251
		- because responsive systems build user confidence.
		  id:: 54cbb347-be89-45ad-bb4c-0ebc20278fc1
	- **Resilient**: A Reactive System remains responsive, even when failures occur.
	  id:: 0b1faa99-c780-4cc4-8613-2939f5fcf91a
		- Resiliency provides responsiveness despite any failures. resiliency depends on [[Replication]], [[isolation]], [[containment]], [[delegation]].
		  id:: 9e711a31-98c9-4c86-acd6-3e9878be3c09
		- Failures should be isolated to a single component and recovery should be delegated to an external components.
		  id:: cdbccd03-6e49-4b6c-8f78-26db1125f945
	- **Elastic**: A Reactive System remains responsive, despite changes at system work load.
	  id:: 988f91fd-2a90-4394-a3af-ef5e96cda2bc
		- Elasticity provides responsiveness for load change  by increasing or decreasing the resources that service the system.
		  id:: 8663713f-9a72-4d83-be16-803a3e962321
		- this proactive auto scaling techniques is also used to support elasticity. Scaling up provides responsiveness during peak, while scaling down improves cost effectiveness.
		  id:: c875506a-246b-4ae7-a172-69e3789ea7b6
		- this should be done through decentralised architecture where there's no contention points or central bottlenecks anywhere in the system.
		  id:: 1ae53dd0-7b1d-455d-a0c0-53a039fe5245
	- **Message Driven**: A Reactive System is built on a foundation of async, non-blocking messages.
	  id:: 137980f7-4d38-4f16-b769-56cc06eab7c4
		- this is the foundation for all of the other reactive principles, Responsiveness, Resilience, Elasticity are supported be a message driven architecture.
		  id:: 0fbd0632-ddff-40aa-8aaf-2886d504b352
		- asynchronous and non-blocking messages is the key element here. it provides loosing coupling, isolation and location transparency and the ability to delegate errors to other parts of the system.
		  id:: 1aa71df5-7fa1-4ccb-8ecd-0d497d2bd9ee
		- this async communication allows resources to be consumed only while active. you don't have a situation when you have a request and this request is blocking the resource and you are stuck waiting for the response from that request and while you are waiting you are consuming resources because you are stuck waiting for a request that may or may not be resolved.
		  id:: d88f1437-5c48-4ca4-9bff-3184650eb041
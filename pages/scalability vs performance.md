---
title: scalability vs performance
---

- distributed systems architecture: The Difference Between Scalability and Performance
  id:: f7eced76-e757-446e-ad78-9bb5f7b422e7
	- Scalability and performance are related but different concepts while **performance optimizes the response time scalability optimizes the ability to handle the load**. Improving the performance speeds up response time but the total number of requests may not change. improving the scalability increases the ability to handle the load but the performance of each request may not change. 
	  id:: 192bedca-35dd-4e3a-9a92-5244206127e6
	- If we look at measurements like requests-per-second you will see that request-per-second actually measures both. that makes it a valuable metric because we can use it to see whether we have improved our performance or our scalability, but it also means that it is somehow restrictive in the sense that while we can use it to see if we have improved either one if it improves we can't tell which one changed. so let's dive into that in more detail. 
	  id:: 0c020ce0-74f3-49a6-842d-a2f81e58bbea
	- For example, if we have a system that takes one second to process a single request and only can process one request at a time that means our request-per-second will be 1. we can handle one more request if we can improve our response time and reduce it from one second to half a second, that means that our requests-per-second has improved and it becomes 2 instead of one. on the other hand, if we take that same one-request-per-sconed system and modify it to handle two requests in parallel that means we also doubled our requests-per-second to become 2. so if we started at one request-per-second and improved the system to be two request-per-second that means whether we have improved our performance or our scalability we may have either one. So it's a valuable metric because it shows that we've made an improvement, but if we want to know where that improvement came from.
	  id:: 4d0167c6-b742-45a2-98ca-e48a4d1fff80
	- **improving performance: **
	  id:: 08e0234f-85d5-441e-8359-a0d5e5ec7b47
		- improving performance will help us to push the graph down which means improving our response time. this has a limit tho we can't push this response time to zero because theoretically, it's impossible. 
		  id:: 2b486c30-595b-41cf-8a90-024b25358578
		- ![improving performance](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2FCkzaWSbGL9.png?alt=media&token=41925dbc-9775-4c55-8df0-11a68f26b441)
		  id:: 1c12508c-c109-4dd6-9c9c-a6c5153cda2e
	- **improving scalability**
	  id:: 7b8e8e23-f19c-49eb-9ac9-cf2226d0b709
		- improving scalability increases our ability to handle the load so that pushes the graph along the y axis, at the same time performance of each request may not change. in theory, there's no limit to increasing scalability but in practice that is usually not the case, there's some limitation that prevents us from going any further, maybe a situation when it becomes too expensive to continue to push it, or maybe it's a limit in a way we designed our software. and because we know that scalability has no theoretical limit to increase it. it means that when we build a software system we tend to focus on improving scalability because we know we can push this "forever".
		  id:: bc11e177-76e6-44fa-8ebc-7df9aa6085f4
		- ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2FKgqDpt0xFs.png?alt=media&token=18ce3ae5-8d10-42c3-8f0a-0fab648bf411)
		  id:: c21d8187-38a5-48ca-8f27-c276245ba090
---
title: temporal decomposition
---

- Temporal Decomposition 
id:: a4e4d55b-4926-4d12-8eef-37e94eff60e7
	 - One common cause of [[information leakage]] is a design style called temporal decomposition. In this style designing a system corresponds to the time order in which operations will occur. Consider an application that reads a file in a particular format modifies the content of the file and then writes the file out again. With Temporal Decomposition this application might be broken into three classes one to read the file, one to perform the modifications, and a third one to write out the new version. both the reading and writing file steps have knowledge about the file format which results in [[information leakage]]  
id:: ef15709c-d7d0-407c-8533-e5bc0a83cbd6

	 - the solution is to combine the core mechanisms reading and writing files into.a single class this class will get used during both the reading and writing phases of the application
id:: 56bf17e2-00f4-471d-aa20-84018f8f2942

	 - it's easy to fall into the trap of temporal decomposition because the order in which operations must occur is often on your mind when you code however, most design decisions manifest themselves at several different times over the life of the application as a result temporal decomposition often results in information leakage. 
id:: 1ad4d168-fe5c-45b2-a18f-49a4dea693be

	 - **when designing modules, focus on the knowledge that needed to perform each task not the order in which tasks occur.**
id:: 0c78c05b-2ab9-4257-bea1-865d463482d3

	 - #[[software design red flags]]
id:: b1544e6b-934a-462a-a373-e619efcafe5e

	 - 
id:: 1cb083d8-8e0a-42cc-b277-d71857e5de8d

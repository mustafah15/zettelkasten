---
title: Types Of Distributed Systems Architectures
---

- types of distributed systems architectures
id:: 1bb7e6c4-9e73-44e5-882d-435ecb0ee12c
	 - Distributed applications and processes typically use one of four architecture types below: 
id:: 34afca3c-62da-48eb-a5db-6509b8b3d86f

	 - client-server
id:: c07aa6cb-8256-43a2-b59a-cef54525904d
		 - in the early days, distributed systems architecture consisted of a server as a shared resource like a printer, database, or web server. it had multiple clients that decide when to use the shared resource, how to use and display it, change data, and send it back to the server. git code repositories are a good example where the intelligence is placed on the developers (clients) committing the changes to the code server.
id:: aa3b3b65-a81b-4387-b539-81ad50893143

	 - three-tier
id:: ffba0050-ce41-4c75-9cd4-5b5a1a513c57
		 - in this architecture, the client no longer needs to be intelligent and can rely on a middle tier to do the processing and decision making. Most of the first web applications fall under this category. the middle tier could be called an agent that receives requests from the client, that could be stateless, processes the data and then forwards it on to the servers.
id:: 9025fbdd-9f0e-43a8-a525-699c8e3196d6

	 - multi-tier
id:: fc5b89d5-d077-4e4d-9c83-494cb6bae16a
		 - Enterprise web services first created n-tier or multi-tier systems architectures. this popularized the application servers that contain the business logic and interact both with the data tiers and presentation tiers.
id:: edf8d776-3c22-4dcd-b772-992d6c1e4741

	 - peer-to-peer
id:: c25f5ed2-dcaa-40c3-9140-5bace126998c
		 - there is no centralized or special machine that does the heavy lifting and intelligent work in this architecture. all the decision making and responsibilities are split up amongst the machines involved and each could take on client or server roles. blockchain is a good example of this.
id:: ed4218de-d488-4f21-8819-5384e350daba

	 - what we are going to discuss mostly will fall under the three-tier and multi-tier categories
id:: c6dab3ec-f095-48aa-8ea2-31b067b21ad1

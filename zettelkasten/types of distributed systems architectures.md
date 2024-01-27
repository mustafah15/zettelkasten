---
tags:
  - software-design
  - distributed-systems
type:
  - literature
related: "[[distributed systems]]"
---

- Distributed applications and processes typically use one of four architecture types below:
- client-server
	- in the early days, distributed systems architecture consisted of a server as a shared resource like a printer, database, or web server. it had multiple clients that decide when to use the shared resource, how to use and display it, change data, and send it back to the server. git code repositories are a good example where the intelligence is placed on the developers (clients) committing the changes to the code server.
- three-tier
	- in this architecture, the client no longer needs to be intelligent and can rely on a middle tier to do the processing and decision making. Most of the first web applications fall under this category. the middle tier could be called an agent that receives requests from the client, that could be stateless, processes the data and then forwards it on to the servers.
- multi-tier
	- Enterprise web services first created n-tier or multi-tier systems architectures. this popularized the application servers that contain the business logic and interact both with the data tiers and presentation tiers.
- peer-to-peer
	- there is no centralized or special machine that does the heavy lifting and intelligent work in this architecture. all the decision making and responsibilities are split up amongst the machines involved and each could take on client or server roles. blockchain is a good example of this.
---
tags:
  - system-design
type: literature
parent: "[[why exception adds complexity]]"
---

 A piece of code may encounter exceptions in several different ways:
	- A caller may provide an argument or config information.
	- An invoked method may not be able to complete a requested operation.
	- network packets may be lost or delayed, servers may not respond in a timely fashion.
	- the code may detect bugs internal inconsistencies or situations it is not prepared to handle.

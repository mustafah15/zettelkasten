---
tags:
  - system-design
  - ddd
type: permanent
parent: "[[Hexagonal Architecture Explained]]"
---

The anti-corruption layer concept from [[domain driven design|DDD]] is broader than the adapter from [[Hexagonal Architecture Explained|Ports and Adapters]] some parts of an ACL may sit inside a port and adapter system and some may sit outside. 

"data is coming from one or more legacy systems. we query the legacy database and rearrange the data into the new concepts in the ACL"


![[Screenshot 2024-11-20 at 08.49.11.png]]


Although you can put ports and boundaries around every bounded context, the Ports & Adapters pattern is really aimed at protecting your team from external technology shifts. Thus, the pattern suggests placing the system boundary just in front of each external technology, keeping the adapters simpler. The advantage of such a boundary is that the team is much more likely to maintain the tests at that boundary than at others.

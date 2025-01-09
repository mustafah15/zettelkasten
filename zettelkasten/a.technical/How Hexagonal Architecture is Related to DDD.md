---
tags:
  - system-design
type: permanent
parent: "[[Hexagonal Architecture Explained]]"
---

[[domain driven design|DDD]] and [[Hexagonal Architecture Explained|Ports and Adapters]] are different concepts; they exist independently they are not explicitly tied to one another, but the two are compatible. you can do DDD without ports and adapters and you can do ports and adapters without DDD. but As it turns out they work really well together. thus, you might consider ports and adapters as an architectural precursor to DDD.


Ports and Adapters simplify code entanglement. By putting all external technologies outside the app, so that the inside only contains domain concepts, you can do your domain-driven design without distraction.

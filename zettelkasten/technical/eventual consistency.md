---
tags:
  - distributed-systems
type:
  - fleeting
related: "[[consistency]]"
---
Eventual consistency guarantees that **in the absence of new updates, all access to a specific piece of data will eventually return the most recent value**. so in order to reach a state of consistency, you have to stop all updates at least for some period of time.
---
aliases:
  - coherency-delay
tags:
  - software-design
  - distributed-systems
related: "[[scalability]]"
---

- In distributed systems synchronizing the state of multiple nodes is done using cross talks, and if we have a system of multiple nodes and in order to reach the state of coherence in the system each node in the system will have to send messages to other nodes informing them of any state change, over time all the nodes will receive the messages notifying them of the new state change and the system will reach the state of coherence.
- The time it takes for system synchronization to complete is called **Coherency Delay**. increasing the number of nodes means increasing this delay.

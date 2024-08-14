---
tags:
  - software-design
  - distributed-systems
type:
  - fleeting
---

- **Definition**: the system continue to operate despite an arbitrary number of messages being dropped or delayed by the network.
- so the reality is no distributed system is safe from the partition, they can occur due to problems in the network, or just a node can go down for one reason or another. so in any of those partition cases we have an interruption in our system communication, these interruptions can be short or long-lived.
- [[CAP Theorem]] has more information how to a distributed system should deal with the partitions.

Fault Tolerance is not the same as Resilency. These two terms are sometimes used interchangeably, but are indeed different.

# Fault Tolerance

- Fault Tolerant means the ability of a system to **survive (tolerate)** when a fault occurs, e.g, surviving a server crash or network partition etc
- There may be some temporary drop in overall performance, however system features are not affected
- Mechanisms such as checkpoint/restore, Replicated State Machines can solve this issue
- The systems usually has the ability to self-detect faults and do failovers

## Example(s)


If out of N instances of a microservice sitting behind a reverse proxy like nginx, one instance fails, the service is still available. However, There will be a decrease in throughput . Hence the service is fault-tolerant.
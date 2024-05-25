---
tags:
  - distributed-systems
type: fleeting
---
Resiliency is a measure of the system's ability to **self-recover** from problems

## Example(s)


- If we run the above example on Kubernetes, the instance that failed will be automatically brought back online (maynot be the same instance) because Kubenetes automatically maintains the exact number of pods in a replica set. Hence in addition to being fault tolerance this it is also resilient
    - Circuit Breaker pattern often used in micro service architecture address resilience issue, wherein you give system time to recover
- In Hadoop or any distributed storage system, if the number of replicas fall below the replication factor, the system creates the number of under-replicated copies automatically

_**You can have a system that is [[partition tolerance]] but not resilient**_. For example, from the first example, if you had to manually bring up an addtional instance
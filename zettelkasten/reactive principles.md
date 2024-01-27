---
tags:
  - system-design
  - distributed-systems
related: "[[reactive distributed systems]]"
type:
  - literature
---
![](https://www.researchgate.net/profile/David-Bauer-7/publication/326960759/figure/fig1/AS:658175791472640@1533932745053/Presentation-of-the-basic-principles-of-reactive-systems-from-the-Reactive-Manifesto.png)
## The Reactive Architecture Principles

### Responsive 
A Reactive system consistently responds in a timely fashion.
- Responsiveness is the cornerstone of system usability, so reactive systems must be fast to detect problems when they begin to arise.
- because responsive systems build user confidence
### Resilient 
 A Reactive System remains responsive, even when failures occur.
 - Resiliency provides responsiveness despite any failures. resiliency depends on Replication, isolation, containment, and delegation.
 - Failures should be isolated to a single component and recovery should be delegated to an external component.
### Elastic
A Reactive System remains responsive, despite changes in system workload
- Elasticity provides responsiveness for load change by increasing or decreasing the resources that service the system.
- This proactive auto-scaling technique is also used to support elasticity. Scaling up provides responsiveness during peak while scaling down improves cost-effectiveness.
- This should be done through decentralized architecture where there are no contention points or central bottlenecks anywhere in the system.
### Message Driven
A Reactive System is built on a foundation of async, non-blocking messages.
- this is the foundation for all of the other reactive principles, Responsiveness, Resilience, and Elasticity are supported by a message-driven architecture.
- asynchronous and non-blocking messages are the key elements here. it provides losing coupling, isolation, and location transparency and the ability to delegate errors to other parts of the system.
- this async communication allows resources to be consumed only while active. you don't have a situation when you have a request and this request is blocking the resource and you are stuck waiting for the response from that request and while you are waiting you are consuming resources because you are stuck waiting for a request that may or may not be resolved.

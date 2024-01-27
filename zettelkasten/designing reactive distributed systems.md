---
tags:
  - distributed-systems
  - system-design
---
These are my notes about the Designing reactive Distributed Systems organised in a way that I see it logical for me, if you want to use the same order that's okay but also feel free to skip to whatever part you find useful for you at that moment.

But before we start we should know what is a distributed system.
- so **the definition** of a [[distributed systems]] is a system with multiple components (nodes) located on different machines that communicate and coordinate actions in order to appear as a single system to the end user.
- why do we need to build a distributed system in the first place?
- distributed systems have endless use cases, a few being electronic banking systems, massively multiplayer online games, or a sensor network.
- another reason for building distributed systems is that some applications require high availability and need to be resilient to single-node failures. some other applications need to tackle workloads that are just too big to fit a single node server, and it has to be scalable enough to handle such high traffic and load, like Google or Facebook where they receive hundreds of thousands of requests per second from all over the globe.
- in this book, we will take a deep look into the main challenges that will face you during designing, and building your distributed systems: [[Communication and Coordination]], [[Scalability]], and [[Partition Tolerance]]. we will discuss what are the best approaches from the reactive architecture point of view.
[[types of distributed systems architectures]]
[[reactive distributed systems]]

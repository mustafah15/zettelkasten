---
tags:
  - system-design
  - distributed-systems
aliases:
  - what is an event bus?
type:
  - literature
---
### What is a messaging system / event-bus?
A **messaging system** is responsible for transferring data among services, applications, processes, or servers. Such a system helps **decouple** different parts of a distributed system by providing an **asynchronous** way of transferring messaging between the sender and the receiver. aka [[distributed systems - async communication|asynchronous communication]] Hence, all senders (or producers) and receivers (or consumers) focus on the data/message without worrying about the mechanism used to share the data.

There are mainly two common ways to handle messages or events
- #### [[message queueing]]
- #### [[publish-subscribe]]




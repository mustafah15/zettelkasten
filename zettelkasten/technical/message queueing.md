---
tags:
  - system-design
  - distributed-systems
type:
  - fleeting
related: "[[distributed systems - async communication|async communication]]"
---
  
In the queuing model, messages are stored sequentially in a queue. Producers push messages to the rear of the queue, and consumers extract the messages from the front of the queue.
A particular message can be consumed by a maximum of one consumer only. Once a consumer grabs a message, it is removed from the queue such that the next consumer will get the next message.
This is a great model for distributing message processing among multiple consumers. But this also limits the system as multiple consumers cannot read the same message from the queue.

![[Screenshot 2023-09-29 at 12.43.04.png]]
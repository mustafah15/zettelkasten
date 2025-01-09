---
tags:
  - output
  - distributed-systems
related: "[[transactional outbox pattern]]"
type: permanent
---


Recently, I was working on a project where I had to implement a feature that required me to send messages to multiple services while saving these messages into the service's internal DB. In this case, the requirement was to guarantee consistency between the system parts (the Message Queue and the Service's DB). This is a well-known problem in the context of distributed systems called the **Dual Write problem**.

The solution for the dual write problem is the transactional outbox pattern, and that's what this blog is about.

The following diagram explains my case: one service that writes to its own DB and a message queue.

![[Screenshot 2024-06-24 at 13.05.27.png]]


To be able to write to both (DB and MQ) in a transactional manner, we need to implement the Outbox Pattern
The first step is to add a new table in the DB, which we'll call the outbox table. We will use it to save the events while we are storing the state info in the DB with a normal DB transaction. If inserting the state in the DB fails for one reason or another, adding the event info to the outbox table will also fail/rollback.

The second step is to create a job that processes the records inside the outbox table and sends them to the Message Queue. Once the job gets the acknowledgment from the message queue that events are received, the job should delete those events from the outbox DB table.

One note on that: if the job receives the acknowledgment from the MQ and, for some reason, fails to delete the events from the outbox DB table, this will lead to the same event being sent again to the MQ. So, our solution guarantees that the event will be sent to the MQ at least once, but maybe more, so the downstream services or the MQ need to handle this case.

![[Screenshot 2024-06-24 at 14.56.43.png]]



Here's A Video Explanation in Arabic:

![](https://youtu.be/mHtTT4SDCvE)


Further resources 
- https://microservices.io/patterns/data/transactional-outbox.html
- https://blog.swcode.io/microservices/2023/10/17/transactional-outbox/ 


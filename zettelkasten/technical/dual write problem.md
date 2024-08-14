---
tags:
  - distributed-systems
type:
  - fleeting
related: "[[transactional outbox pattern]]"
---
A dual write problem happens when you have a service that should write or update two different systems for example a database and message queue if one operation fails then we will have an inconsistent system for example we updated the database and were not able to update the message system or the opposite updating the message system and were not able to update the database this is known as the [[dual write problem]] which is common issue in distributed systems
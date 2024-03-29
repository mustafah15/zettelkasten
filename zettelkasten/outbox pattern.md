---
tags:
  - system-design
  - distributed-systems
type:
  - literature
---
## Problem 

A [[dual write problem]] happens when you have a service that should write or update two different systems for example a database and message queue if one operation fails then we will have an inconsistent system for example we updated the database and were not able to update the message system or the opposite updating the message system and were not able to update the database this is known as the [[dual write problem]] which is common issue in distributed systems

## Solution

this problem can be solved by implementing the outbox pattern which works as follows:

- continue to save your state into the database but also add a new record to a newly created table "outbox" which contains all the event information. 
- Another process should start when there is a new record inserted in this table "outbox" this process should send the update to the message system
- when the message is successfully sent this event record should marked as done or to be deleted from the outbox table to avoid sending it again
![](https://miro.medium.com/v2/resize:fit:700/0*Ac8lQUigqikXPIVF.png)
## Implementation 


outbox pattern vs saga pattern
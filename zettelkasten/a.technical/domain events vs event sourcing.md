---
tags:
  - ddd
  - distributed-systems
type: permanent
---
Event sourcing is a way to store the state of the object. Instead of storing just the current state of the object, use an append-only store to record the full series of changes taken on that object.

Domain Events and Event Sourcing are easy to be mixed up because they both relate to “event” and sometimes they can be used to together, but they are absolutely different concepts.

- Domain events: something happened in the domain
- Event sourcing: a way to store the state of domain object.

related:  
- [[event sourcing]]
- [[ddd domain event]]
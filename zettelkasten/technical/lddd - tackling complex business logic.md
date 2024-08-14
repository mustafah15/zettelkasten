---
tags:
  - ddd
  - system-design
related: "[[learning domain driven design]]"
type:
  - literature
---
we have been introduced to the [[lddd - implementing simple business logic]] in this part we will study a few patterns to help us tackle complex logic.


## Domain Model

The domain model pattern is intended to cope with cases of complex business logic, instead of CRUD interfaces we deal with 
- complicated state transitions
- business rules and invariants rules that have to be protected at all times.
### Implementation 
A domain model is an object model of the domain that incorporates both behavior and data. DDD tactical patterns (aggregates, value objects, domain events, and domain services) are the building blocks of such an object model
All of these patterns out the business logic first.
#### Implementation Complexity 
The domain business logic is already inherently complex so the objects used for modeling it should not introduce any additional accidental complexities. the model should be devoid of any infrastructure or technological concerns, this restriction requires the model's objects to be plain old objects, objects implementing business logic without relying on or directly incorporating any infrastructural components or frameworks.

#### Implementation ubiquitous language 
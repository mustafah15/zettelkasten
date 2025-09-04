---
tags:
  - ddd
  - software-design
parent: "[[DDD - tactical patterns]]"
type: permanent
---
- Aggregates
    Aggregate is a specific type of Entity
    - An Aggregate is a collection of domain objects bound to a root entity.
    - The root entity is called the Aggregate root.
    - Objects in an aggregate can be treated as a single unit.
    - Access to objects in the aggregate must go through the aggregate root.
    - Transaction should not span multiple Aggregate Roots.
    - Aggregates are good candidates for distribution in a Reactive System.
    - ![[aggregate.png]]
- **Determining the Aggregate Roots**
	- Choosing an aggregate root is not always straightforward.
	- the aggregate root can be different from one context to another.
	- some contexts may require multiple aggregate roots.
	- some questions to consider:
	    - is the entity involved in most operations in that bounded context?
	    - if you delete the entity, does it require you to delete other entities?
	    - will a single transaction span multiple entities?
	- ![[aggroot.png]]
- 
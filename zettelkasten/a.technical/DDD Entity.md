---
tags:
  - ddd
  - software-design
parent: "[[DDD - tactical patterns]]"
type: permanent
---

- Entities
    - An Entity is defined by a unique identity
    - An Entity May change its attributes but not its identity.
    - If the Identity changes, it is a new entity regardless of it's attributes.
    - Entities are the single source of truth for a particular id.
    - Entities can also Contain business logic

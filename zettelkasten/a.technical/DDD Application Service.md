---
tags:
  - ddd
  - software-design
parent: "[[DDD - tactical patterns]]"
type: permanent
---
the purpose is Orchestrates **use cases** and coordinates domain objects and services.
Typically **stateless** too, but may manage transactions, workflows, and security.
it can potentially know Domain objects, domain services, repositories, and sometimes infrastructure.
- its **Responsibilities** is to Receive commands (from UI, API, etc.)- Coordinate domain services and repositories- Manage transaction boundaries. 
- it can depend on infrastructure as it's part of the application layer
- 

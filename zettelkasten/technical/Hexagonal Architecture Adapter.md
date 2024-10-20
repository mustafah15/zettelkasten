---
tags:
  - ddd
  - system-design
related: "[[Hexagonal Architecture Glossary]]"
type: permanent
aliases:
  - Adapter
---
## Adapter 
The code needed to fit the interfaces defined by the app with those actors, an adapter translates requests from an external actor linked to a specific technology into technology-neutral requests at a port and vice versa.

### Primary Adapter
An adapter that connects a primary [[Hexagonal Architecture Actor|Actor]] to a primary [[Hexagonal Architecture Port|Port]]

### Secondary Adapter
An adapter that connects a Secondary [[Hexagonal Architecture Actor|Actor]] to a Secondary [[Hexagonal Architecture Port|Port]]

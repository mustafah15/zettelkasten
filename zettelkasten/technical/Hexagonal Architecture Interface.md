---
tags:
  - ddd
  - system-design
related: "[[Hexagonal Architecture Glossary]]"
type: permanent
aliases:
---
## Interface

A set of methods definitions declared by an actor, specifying a contract to be fulfilled by the one that realises (implements) the interface.

### Provided Interface 
An interface that defines the services offered by the app and is used by the driving [[Hexagonal Architecture Interactor|Interactor]] 

### Required Interface 
An interface that defines the services needed by the app to perform its function. it is used by the app and implemented by the driven [[Hexagonal Architecture Actor|Actor]]

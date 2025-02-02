---
tags:
  - book-notes
  - ddd
related: "[[what is a bounded context|lddd - what is a bounded context]]"
aliases:
  - Scope of a Bounded Context
type: literature
---

### Scope of a Bounded Context 
Since different domain experts can hold conflicting mental models of the same business entity to model the business domain, we had to divide the model and define a strict applicability context for each fine-grained model - its bounded context
The consistency of the ubiquitous language only helps to identify the widest boundary of the language it cannot be any larger, because then there will be inconsistent models and terminology. However, we can still further decompose the models into even smaller bounded contexts, defining the scope of a ubiquitous language and its bounded context is a strategic design decision
![[Screenshot 2024-02-08 at 07.37.09.png]]

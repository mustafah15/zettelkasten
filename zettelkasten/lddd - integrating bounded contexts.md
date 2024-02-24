---
tags:
  - book-notes
  - ddd
related: "[[learning domain driven design|lddd]]"
type:
  - literature
---
not only does the bounded context protect the consistency of a ubiquitous language but it also enables modeling, you can't build a model without specifying its purpose and its boundary the boundary divides the responsibility of languages as A language in one bounded context can model the business domain to solve a particular problem another bounded context can represent the same business entities but model them to solve a different problem. 

Bounded contexts themselves are not independent just as a system cannot be built out of independent components the components have to interact with one another to achieve  the system's overarching goals, and so too do the implementations in bounded contexts although they can evolve independently they have to integrate as a result there will always be touch points between bounded context these are called ==Contracts==

Why contracts are needed in the context of DDD?
The need for contracts results from differences in bounded contexts models and languages Since each contract affects more than one party they need to be defined and coordinated also by definitions two bounded contexts are using different ubiquitous languages which language will be used for integration purposes? these integration concerns should be addressed by the solution's design. 

DDD Patterns for defining relationships and integration between bounded contexts

Cooperation, Customer-Supplier, and Separate Ways.

## [[lddd - integrating bounded context with cooperation pattern]]

## [[lddd - integrating bounded context with customer-supplier pattern]]

## [[lddd - integrating bounded context with separate-ways or duplication]]

## [[bounded context - context map]]

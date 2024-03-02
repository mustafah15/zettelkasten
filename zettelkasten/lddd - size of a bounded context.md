---
tags:
  - book-notes
  - ddd
type:
  - literature
related: "[[lddd - what is a bounded context?|lddd - what is a bounded context]]"
---

### Bounded Context Sizing 
a bounded context's size by itself is not a deciding factor, models shouldn't necessarily be big or small. models need to be useful. the wider the boundary of the ubiquitous language is the harder it is to make it consistent. it may be beneficial to divide a large ubiquitous language into a smaller, more manageable problem domain but striving for domain-bounded context can backfire too. the smaller they are the more integration overhead the design induces.
The reason for extracting finger-grained bounded context out of a larger one includes constituting new software engineering teams or addressing some of the system's non-functional requirements; for example, when you need to separate the development lifecycle of some of the components originally residing in a single bounded context pendently from the rest of the bounded context's functionalities. one thing to beware of is splitting a coherent functionality into multiple bounded contexts such division will hinder the ability to evolve each context independently. instead the same business requirements and changes will simultaneously affect the bounded contexts and require simultaneous deployment of changes to avoid such ineffective decomposition, use the rule of thumb ( to find subdomains identify sets of coherent use cases that operate on the same data, and avoid decomposing them into multiple bounded contexts )
---
tags:
  - book-notes
  - ddd
related: "[[lddd - managing domain complexity]]"
type:
  - literature
---

## Boundaries 
the bounded context pattern is the domain-driven design tool for defining physical and ownership boundaries.

### Physical Boundaries 

Bounded contexts serve not only as model boundaries but also as physical boundaries of the systems implementing them, each bounded context should be implemented as an individual service/project, meaning it is implemented, evolved, and versioned independently of the other bounded contexts
clear physical boundaries between bounded contexts allow us to implement each bounded context with the technology stack that best fits its needs.

A bounded context can contain multiple subdomains in such a case the bounded context is a physical boundary while each of its subdomains is a logical boundaries that bear different names in different programming languages (namespaces, modules, or packages)

### Ownership boundaries 
In software projects, we can leverage model boundaries aka bounded contexts for the peaceful coexistence of teams. the division of work between teams is another strategic decision that can be made using the bounded context pattern.
A Bounded context should be implemented, evolved, and maintained by one team ONLY. no two teams can work in the same bounded context this segregation eliminates implicit assumptions that teams might make about one another's models. instead, they have to define communication protocols for integrating their models and systems explicitly. 

> [!note]+
> It's important to note that the relationship between teams and bounded context is one-directional: a bounded context should be owned by only one team, however a single team can own multiple bounded contexts
> 

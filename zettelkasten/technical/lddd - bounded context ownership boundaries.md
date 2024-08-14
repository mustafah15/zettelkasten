---
tags:
  - book-notes
  - ddd
related: "[[lddd - building boundaries with bounded context]]"
type:
  - literature
---
### Ownership boundaries 
In software projects, we can leverage model boundaries aka bounded contexts for the peaceful coexistence of teams. the division of work between teams is another strategic decision that can be made using the bounded context pattern.
A Bounded context should be implemented, evolved, and maintained by one team ONLY. no two teams can work in the same bounded context this segregation eliminates implicit assumptions that teams might make about one another's models. instead, they have to define communication protocols for integrating their models and systems explicitly. 

> [!note]+
> It's important to note that the relationship between teams and bounded context is one-directional: a bounded context should be owned by only one team, however a single team can own multiple bounded contexts
> 

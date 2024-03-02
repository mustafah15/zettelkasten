---
tags:
  - book-notes
  - ddd
type:
  - literature
related: "[[lddd - building boundaries with bounded context]]"
---

### Physical Boundaries 

Bounded contexts serve not only as model boundaries but also as physical boundaries of the systems implementing them, each bounded context should be implemented as an individual service/project, meaning it is implemented, evolved, and versioned independently of the other bounded contexts
clear physical boundaries between bounded contexts allow us to implement each bounded context with the technology stack that best fits its needs.

A bounded context can contain multiple subdomains in such a case the bounded context is a physical boundary while each of its subdomains is a logical boundaries that bear different names in different programming languages (namespaces, modules, or packages)
---
tags:
  - ddd
  - software-design
type: literature
related: "[[active record pattern]]"
---

### When To Use Active Record


Because an active record is essentially a [[transaction script pattern]] that optimizes access to the database this pattern can only support relatively simple business logic such as CRUD operations which at most validate the users input

Active Record Pattern lends itself to supporting subdomains, integration of external solutions for generic subdomains or model transformation tasks

Active Record is also known as an anemic domain model antipattern; or an improperly designed domain model, Note that this pattern is a tool like any other tool but it can potentially introduce more harm when applied in the wrong way


https://softwareengineering.stackexchange.com/questions/70291/what-are-the-drawbacks-to-the-activerecord-pattern

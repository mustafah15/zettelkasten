---
tags:
  - system-design
  - book-notes
  - ddd
type: permanent
parent: "[[Hexagonal Architecture Explained]]"
---
Pat Maddox, at the conference, sat with Alistair later. Together they worked through the evolution of a CQRS architecture and related design patterns. The conclusion was that CQRS might use Ports & Adapters, but it was not, in itself, an example of Ports & Adapters. See [here](https://www.youtube.com/watch?v=9kQ2veoeWZM)

Both the Command and Query sections of CQRS are bounded subsystems. If they are decoupled from the driving and driven technologies, as per Component + Strategy, then they form examples of Ports & Adapters. We write “if”, because there is nothing in the CQRS architecture to prevent you from coupling those elements directly to the technologies and having the same difficulties as any other system design with such direct coupling. Thus, these are great examples of how to use the Ports & Adapters architecture in a larger system. However, a total CQRS system is composed not only of those business logic parts, but also of the external technology parts, specifically the repositories and the UI. The total system itself is not an example of Hexagonal / Ports & Adapters.

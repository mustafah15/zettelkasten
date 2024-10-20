---
tags:
  - ddd
  - book-notes
  - software-design
related: "[[Hexagonal Architecture Explained]]"
type: permanent
---

#### Testing
you can write and run tests at the system level without a production connection, making them purer and faster, also you can swap out the production connections for test and vice versa for any of the connections, input or output without having to rebuild your system.

#### [[POSD - information leakage|Information Leakage]] Protection
The test wall around your application layers will detect whenever someone leaks ui details or technology details into your business logic

#### Large System Separations 
Different teams can develop and own their sections of code independently, test them separately and connect them according to defined and tested interfaces.

#### Long-running systems
you can replace one external connection with another easily as technology and business needs change over the years.

Domain Driven Design:
Once the technology elements are safely outside the application boundary, you can focus on the domain design without distraction.


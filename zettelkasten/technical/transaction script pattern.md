---
tags:
  - book-notes
  - ddd
  - software-design
related: "[[lddd - implementing simple business logic]]"
type:
  - literature
---
"Organizes business logic by procedures where each procedure handles a single request from the presentation" -Martin Fowler

This pattern sees the system's public interface as a collection of business transactions that consumers can execute, these transactions can retrieve/modify information managed by the system. In effect, this pattern uses the system public in operations as encapsulation boundaries. 

### Implementation 
Each procedure is implemented as a simple, straightforward procedural script, it can use a thin abstraction layer of integrating with storage mechanisms, but it is also free **to access the database directly**
The only requirement procedures have to fulfill is their transactional behavior, Each operation should either succeed or fail but can never result in an invalid state. Even if the execution of a transaction script fails at the most inconvenient moment the system should remain consistent 

### It's not that easy
Note that the transaction script pattern is a foundation for the more advanced business logic implementation patterns. also despite its apparent simplicity, it is easy that go wrong with implementing this pattern 

### [[3 ways to corrupt your data when using transaction script]]

### when to use transaction script
the transaction script is well adapted to the most straightforward problem domains in which the business logic resembles simple procedural operations.
which make it naturally fit [[lddd - supporting subdomain]] it also can be used as an adapter for integration with external systems

the main advantage of the transaction script is its simplicity it introduces minimal abstraction and minimizes the overhead both in runtime performance and in understanding the business logic that said this simplicyt is also the pattern's disadvantage the more complex the business logic gets the more it's prone to duplicate business logic gets, the more its prone to duplicate business logic across transactions and consequently to result in inconsistent behavior 


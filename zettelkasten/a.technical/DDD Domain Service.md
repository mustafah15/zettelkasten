---
tags:
  - ddd
  - software-design
parent: "[[DDD - tactical patterns]]"
type: permanent
---
- **Definition**: A stateless service that encapsulates domain logic that doesn’t naturally fit within an Entity or Value Object.
- **Example**: PaymentProcessingService, CurrencyConversionService.
- **Use Case**: When business logic spans multiple entities or is too complex to live in one model.

- Encapsulates **domain logic** that doesn’t naturally belong to an Entity or Value Object.
- **Stateless** – no internal state, operates purely on arguments and returns results.
- Deals only with **domain concepts** (entities, value objects, domain rules).
- Enforce domain invariants- Implement business rules involving multiple entities- Act like a verb in the domain.
- Should be **pure domain logic** – no DB, messaging, etc

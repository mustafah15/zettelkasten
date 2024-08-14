---
tags:
  - book-notes
  - ddd
related: "[[lddd - integrating bounded contexts]]"
type:
  - literature
aliases:
  - customer-supplier pattern
---

The second group of collaboration patterns is the customer-supplier where is one of the bounded contexts the supplier provides a service for its customers the service provider is the upstream and the customer is the downstream.

![[Screenshot 2024-02-21 at 08.34.43.png]]
unlike the [[lddd - integrating bounded context with cooperation pattern]] case both upstream and downstream can succeed independently. In most cases we have an imbalance of power: either the upstream or the downstream team can dictate the integration contract.

### [[lddd - integrating bounded contexts with conformist pattern|conformist]]

### [[lddd - integrating bounded contexts with anticorruption layer|anti-corruption layer]]

### [[lddd - integrating bounded contexts with open-host service|open-host service pattern]]
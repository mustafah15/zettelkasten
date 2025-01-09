---
tags:
  - database
type: permanent
parent: "[[database isolation levels]]"
---
**read committed**: each query in a transaction only sees committed changes by other transactions.
- pros: you will not get a [[database dirty reads]]
- cons: you still can get the other [[database read phenomenas]]
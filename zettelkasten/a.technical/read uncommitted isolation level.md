---
tags:
  - database
type: permanent
parent: "[[database isolation levels]]"
---

**read uncommitted**: no isolation, any change form the outside is visible to the transaction committed or not.

- pros: fast
- cons: you can easily get [[database dirty reads]]
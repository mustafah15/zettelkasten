---
tags:
  - database
type: permanent
parent: "[[database isolation levels]]"
---
**snapshot**: every query in a transaction only sees changes that have been committed up to the start of the transaction it's like a snapshot version of the database at the moment of the transaction start.
- pros: you will avoid every [[database read phenomenas]]
- cons: still might be slow and expensive if you use this for all your transactions

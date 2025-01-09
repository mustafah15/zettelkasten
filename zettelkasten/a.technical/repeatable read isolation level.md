---
tags:
  - database
type: permanent
parent: "[[database isolation levels]]"
---
**repeatable read**: the transaction will make sure that when a query reads a row that row will remain unchanged while the transaction is running

- pros: certainly you will avoid [[database dirty reads]] & [[database non-repeatable reads]]
- cons: might be slow and you still can get [[database phantom reads]]
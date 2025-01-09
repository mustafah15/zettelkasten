---
tags:
  - database
related: "[[database read phenomenas]]"
type: permanent
---
### what is an "isolation level"
**Database isolation** refers to the ability of a database to allow a transaction to execute as if there are no other concurrently running transactions (even though in reality there can be a large number of concurrently running transactions). The overarching goal is to prevent reads and writes of temporary, aborted, or otherwise incorrect data written by concurrent transactions.

- [[read uncommitted isolation level]]
- [[read committed isolation level]]
- [[repeatable read isolation level]]
- [[snapshot isolation level]]
- [[serializable isolation level]]






- 



![[isolation levels.png]]
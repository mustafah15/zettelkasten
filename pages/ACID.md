---
title: ACID
---

- **Transaction is a collection of queries that form a transaction** see [[database transaction]]
-
- A transaction is a collection of instructions. to maintain the integrity of a database, all transactions must obey ACID properties.  ACID stands for atomicity, consistency, isolation and durability.
	- **Atomicity**
	- **A transaction is an atomic unit; as all the instructions within a transaction will successfully execute, or none of them will execute.** The following transaction transfers 20 dollars from a bank account to another bank account. if any of the instructions fail, the entire transaction should abort and roll back. an atomic transaction is a transaction that will rollback all queries if one or more queries failed.
	- **Consistency**
		- A database is initially in a consistent state, and it should remain consistent after every transaction. suppose that the transaction in the previous example fails after writing and the transaction is not rolled back then the database will be inconsistent as the sum of the money in each account will not be equal to the amount of the money they had before the transaction.
	- [[Consistency in Databases]]
	- **Isolation**
		- If the multiple transactions are running concurrently, they should not be affected by each other; the result should be the same as the result obtained if the transactions were running sequentially.
		- [[database isolation]]
	- **Durability**
		- Changes that have been committed to the database should remain even in the case of software and hardware failure. for instance, if x account contains 10$ this information should not disappear upon hardware or software failure.
		- [[database durability]]
		-
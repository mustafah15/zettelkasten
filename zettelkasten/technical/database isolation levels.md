---
tags:
  - database
type:
  - fleeting
related: "[[database read phenomenas]]"
---
### what is an "isolation level"
**Database isolation** refers to the ability of a database to allow a transaction to execute as if there are no other concurrently running transactions (even though in reality there can be a large number of concurrently running transactions). The overarching goal is to prevent reads and writes of temporary, aborted, or otherwise incorrect data written by concurrent transactions.

- **read uncommitted**: no isolation, any change form the outside is visible to the transaction committed or not.
	- pros: fast
	- cons: you can easily get [[database dirty reads]]
- **read committed**: each query in a transaction only sees committed changes by other transactions.
	- pros: you will not get a [[database dirty reads]]
	- cons: you still can get the other [[database read phenomenas]]
- **repeatable read**: the transaction will make sure that when a query reads a row that row will remain unchanged while the transaction is running
	- pros: certainly you will avoid [[database dirty reads]] & [[database non-repeatable reads]]
	- cons: might be slow and you still can get [[database phantom reads]]
- **snapshot**: every query in a transaction only sees changes that have been committed up to the start of the transaction it's like a snapshot version of the database at the moment of the transaction start.
	- pros: you will avoid every [[database read phenomenas]]
	- cons: still might be slow and expensive if you use this for all your transactions
- **serializable**: transaction are run as if they serialized one after the other so no concurrency anymore.


![[isolation levels.png]]
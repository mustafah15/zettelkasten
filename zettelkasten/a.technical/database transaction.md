---
tags:
  - database
type: permanent
parent: "[[database engineering]]"
deeper: "[[why do you need a read-only database transaction]]"
folgezettel: 3a2g3
---

DEF: A database transaction is a collection of queries that are treated as one unit of work

- transaction lifespan
	- transaction BEGIN
	- transaction COMMIT
	- transaction ROLLBACK
- transaction unexpected ending = ROLLBACK (eg. crash) if something went wrong.

- transactions are used to change and modify data, but it's also perfectly normal to have a read-only transaction.


[[why do you need a read-only database transaction]]

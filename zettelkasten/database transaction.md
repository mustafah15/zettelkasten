---
tags:
  - database
type:
  - fleeting
related: "[[database engineering]]"
---

DEF: A database transaction is a collection of queries that are treated as one unit of work

- transaction lifespan
	- transaction BEGIN
	- transaction COMMIT
	- transaction ROLLBACK
- transaction unexpected ending = ROLLBACK (eg. crash) if something went wrong.

- transactions are used to change and modify data, but it's also perfectly normal to have a read-only transaction.


- ### why you might need to do a read-only database transaction?
	- **Consistency and data integrity**: By performing read-only transactions, you can ensure that the data you retrieve remains consistent throughout the transaction. It prevents any accidental modifications or updates to the data, maintaining the integrity of the database.
	- **Security and audit purposes**: In certain scenarios, ensuring the data remains unchanged for security or auditing reasons is essential. For example, financial systems may require immutable records to maintain an accurate audit trail.
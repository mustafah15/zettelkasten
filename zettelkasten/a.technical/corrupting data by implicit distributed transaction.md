---
tags:
  - ddd
  - system-design
type: permanent
parent: "[[how transaction script pattern can lead to data corruption]]"
---

### corrupting data by implicit distributed transaction

```PHP
class LogVist {

	public Execute($userId, $visitedOn) {
		db.execute("update users set last_visited '$visitedOn' where user_id='$userId'")
	}
}
```
instead of tracking the last visit date as in the previous examples this method maintains a counter of visits for each user. calling the method increases the corresponding counter's values by 1. All the method does is update one value, in one table residing in one database yet this is still a distributed transaction that can potentially lead to an inconsistent state, because it communicates information to the database and the internal and external process that called the method can fail for one reason or another while writing to the db.

---
tags:
  - ddd
  - system-design
type: permanent
parent: "[[how transaction script pattern can lead to data corruption]]"
---

### corrupting data by lack of transactional behaviour
a trivial example of failing to implement transactional behavior is issuing multiple updates without an overarching transaction consider the following code

```PHP
class LogVist {

	public Execute($userId, $visitedOn) {
		db.execute("update users set last_visited '$visitedOn' where user_id='$userId'")
		db.execute("insert into visitslog (user_id, visit_date) vlaues ('$userId', '$visitedOn')")
	}
}
```

if any issues occur after the record in the user table was updated in the first db execution the system will end up in an inconsistent state the user table will be updated but no corresponding record will be written to the `visitLog` table. this issue can be due to anything from a network outage to a database timeout or deadlock. this issue can be easily fixed by applying a proper db transaction mechanism which can be easy to implement due to relational database native support of transaction.

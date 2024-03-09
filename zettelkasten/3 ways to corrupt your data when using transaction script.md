---
tags:
  - ddd
  - book-notes
related: "[[transaction script pattern]]"
type:
  - literature
---

### lack of transactional behavior
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

### Distributed transaction
In common distributed systems it's common practice to make changes to the data in a database and then notify other components of the system about the change by async communication methods (message or event) consider the previous example instead of logging a visit in a table we have to publish to a message bus
```PHP
class LogVist {

	public Execute($userId, $visitedOn) {
		db.execute("update users set last_visited '$visitedOn' where user_id='$userId'")
		messanger.publish("VISITS_TOPIC", [user_id => $userId, visitDate => $visitedOn])
	}
}
```

As in the previous example any failure occurring after the line of db insertion will corrupt the system's state the user's table will be updated but the other components won't be notified as publishing to the message bus has failed.

fixing this issue is not as easy as in the previous example distributed transactions spanning multiple storage mechanisms are complex and hard to scale error-prone and therefore are usually avoided
### implicit distributed transaction

```PHP
class LogVist {

	public Execute($userId, $visitedOn) {
		db.execute("update users set last_visited '$visitedOn' where user_id='$userId'")
	}
}
```
instead of tracking the last visit date as in the previous examples this method maintains a counter of visits for each user. calling the method increases the corresponding counter's values by 1. All the method does is update one value, in one table residing in one database yet this is still a distributed transaction that can potentially lead to an inconsistent state, because it communicates information to the database and the internal and external process that called the method can fail for one reason or another while writing to the db.

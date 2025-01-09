---
tags:
  - ddd
  - system-design
type: permanent
parent: "[[how transaction script pattern can lead to data corruption]]"
---

### corrupting data by distributed transaction
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
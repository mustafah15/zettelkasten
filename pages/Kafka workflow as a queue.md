---
title: Kafka workflow as a queue
---

- This can be done with consumer group

- Instead of a single consumer, a group of consumers from one consumer group subscribes to a topic, and the messages are shared among them. Let us check the workflow of this system:
	 - Producers publish messages on a topic.

	 - Kafka stores all messages in the partitions configured for that particular topic, similar to [[Kafka workflow as a pub-sub]].

	 - A single consumer subscribes to a specific topic, assume Topic-01 with Group ID as Group-1.

	 - Kafka interacts with the consumer in the same way as pub-sub messaging until a new consumer subscribes to the same topic, Topic-01, with the same Group ID as Group-1.

	 - Once the new consumer arrives, Kafka switches its operation to share mode, such that each message is passed to only one of the subscribers of the consumer group Group-1. This message transfer is similar to queue-based messaging, as only one consumer of the group consumes a message. Contrary to queue-based messaging, messages are not removed after consumption.

	 - This message transfer can go on until the number of consumers reaches the number of partitions configured for that particular topic.

	 - Once the number of consumers exceeds the number of partitions, the new consumer will not receive any message until an existing consumer unsubscribes. This scenario arises because each consumer in Kafka will be assigned a minimum of one partition. Once all the partitions are assigned to the existing consumers, the new consumers will have to wait.

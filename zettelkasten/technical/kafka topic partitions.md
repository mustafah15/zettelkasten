---
tags:
  - distributed-systems
  - system-design
type:
  - literature
related: "[[kafka]]"
---
Kafka topics are partitioned, meaning a topic is spread over a number of ‘fragments’. Each partition can be placed on a separate Kafka broker. When a new message is published on a topic, it gets appended to one of the topic’s partitions. The producer controls which partition it publishes messages to based on the data. For example, a producer can decide that all messages related to a particular ‘city’ go to the same partition.
Essentially, a partition is an ordered sequence of messages. Producers continually append new messages to partitions. Kafka guarantees that all messages inside a partition are stored in the sequence they came in. **Ordering of messages is maintained at the partition level, not across the topic.**
![[kafka partitions.png]]
A unique sequence ID called an **offset** gets assigned to every message that enters a partition. These numerical offsets are used to identify every message’s sequential position within a topic’s partition.
Offset sequences are unique only to each partition. This means, to locate a specific message, we need to know the **Topic, Partition, and Offset number.**
Producers can choose to publish a message to any partition. If ordering within a topic is not needed, a round-robin partition strategy can be used, so records get distributed evenly across partitions.
Placing each partition on separate Kafka brokers enables multiple consumers to read from a topic in parallel. That means, different consumers can concurrently read different partitions present on separate brokers.
Placing each partition of a topic on a separate broker also enables a topic to hold more data than the capacity of one server.
A producer can add a ‘**key**’ to any message it publishes. Kafka guarantees that messages with the same key are written to the same partition. (partition_key)
Kafka follows the principle of a **dumb broker** and **smart consumer**. This means that Kafka does not keep track of what records are read by the consumer. Instead, consumers, themselves, poll Kafka for new messages and say what records they want to read. This allows them to increment/decrement the offset they are at as they wish, thus being able to replay and reprocess messages. Consumers can read messages starting from a specific offset and are allowed to read from any offset they choose. This also enables consumers to join the cluster at any point in time.
Every topic can be replicated to multiple Kafka brokers to make the data fault-tolerant and highly available. Each topic partition has one leader broker and multiple replica (follower) brokers.

- leader
	- A leader is the node responsible for all reads and writes for the given partition. every partition has one Kafka broker acting as a leader.
- Follower
	- To handle single point of failure, Kafka can replicate partitions and distribute them across multiple broker servers called followers. Each follower’s responsibility is to replicate the leader’s data to serve as a ‘backup’ partition. This also means that any follower can take over the leadership if the leader goes down.
	- In the following diagram, we have two partitions and four brokers. Broker 1 is the leader of Partition 1 and follower of Partition 2. Consumers work together in groups to process messages efficiently. More details on consumer groups later.
	- Kafka stores the location of the leader of each partition in ZooKeeper. As all writes/reads happen at/from the leader, producers and consumers directly talk to ZooKeeper to find a partition leader
- .![[kafka_follower_leader.png]]



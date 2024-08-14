---
tags:
  - system-design
  - distributed-systems
type:
  - literature
related: "[[kafka]]"
---


- **Brokers**
	- Brokers are responsible for reliably storing data provided by the producers and making it available to the consumers. A kafka server is also called a broker.
- **Records**
	- a record is a message or an event that gets stored in kafka. Essentially, it is the data that travels from producer to consumer through kafka. a record contains a ke a value a timestamp and optional metadata headers.
- **Topics**
	- Kafka divides its messages into categories called Topics. In simple terms, a topic is like a table in a database, and the messages are the rows in that table.
	- Each message that Kafka receives from a producer is associated with a topic.
	- Consumers can subscribe to a topic to get notified when new messages are added to that topic.
	- A topic can have multiple subscribers that read messages from it.
	- In a Kafka cluster, a topic is identified by its name and must be unique.
	- Messages in a topic can be read as often as needed — unlike traditional messaging systems, messages are not deleted after consumption. Instead, Kafka retains messages for a configurable amount of time or until a storage size is exceeded. Kafka’s performance is effectively constant with respect to data size, so storing data for a long time is perfectly fine.
- **Producers**
	- Producers are applications that publish (or write) records/messages to the Kafka broker
- **Consumers**
	- Consumers are the applications that subscribe to (read and process) data from Kafka topics. Consumers subscribe to one or more topics and consume published messages by pulling data from the brokers.
	- In Kafka, producers and consumers are fully decoupled and agnostic of each other, which is a key design element to achieve the high scalability that Kafka is known for. For example, producers never need to wait for consumers.

![[kafka_cluster.png]]
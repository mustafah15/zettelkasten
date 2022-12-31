---
title: What is Kafka?
---

- What Is Kafka?
	 - Apache Kafka is an open-source **publish-subscribe**-based messaging system __Kafka can work as a message queue too__,  It is distributed, durable, fault-tolerant, and highly scalable by design. Fundamentally, it is a system that takes streams of messages from applications known as producers, stores them reliably on a central cluster (containing a set of brokers), and allows those messages to be received by applications (known as consumers) that process the messages.

	 - Kafka was created at LinkedIn around 2010 to track various events, such as page views, messages from the messaging system, and logs from various services. Later, it was made open-source and developed into a comprehensive system which is used for:
		 - Reliably storing a huge amount of data.

		 - Enabling high throughput of message transfer between different entities.

		 - Streaming real-time data.

	 - At a high level, we can call Kafka a distributed **Commit Log**. A [[Commit Log]] (__also known as a Write-Ahead log or a Transactions log__) is an **append-only** data structure that can persistently store a sequence of records. Records are always appended to the end of the log, and once added, records cannot be deleted or modified. Reading from a commit log always happens from left to right (__or old to new__).
		 - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2FoF0FNV5Zxo.png?alt=media&token=d45c4dd7-f793-4afe-a54e-197500703d32)

		 - Kafka stores all of its messages on the disk. Since all reads and writes happen in sequence, Kafka takes advantage of sequential disk reads.

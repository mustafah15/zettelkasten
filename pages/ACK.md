---
title: ACK
---

- An acknowledgement (ACK) is a signal passed between communicating processes to signify acknowledgement, i.e., receipt of the message sent. The ack-value is a producer configuration parameter in Apache Kafka and can be set to the following values:

- **acks=0** The producer never waits for an ack from the broker when the ack value is set to 0. **No guarantee can be made that the broker has received the message**. The producer doesn’t try to send the record again since the producer never knows that the record was lost. This setting provides lower latency and higher throughput at the cost of a much higher risk of message loss.

- **acks=1** When setting the ack value to 1, the producer gets an ack after the leader has received the record. The leader will write the record to its log but will respond without awaiting a full acknowledgement from all followers. The message will be lost only if the leader fails immediately after acknowledging the record, but before the followers have replicated it. This setting is the middle ground for latency, throughput, and durability. It is slower but more durable than acks=0.

- **acks=all** Setting the ack value to all means that the producer gets an ack when all in-sync replicas have received the record. The leader will wait for the full set of in-sync replicas to acknowledge the record. This means that it takes a longer time to send a message with ack value all, but it gives the strongest message durability.

- How to set the Apache Kafka ack-value
	 - For the highest throughput set the value to 0. For no data loss, set the ack-value to all (or -1). For high, but not maximum durability and for high but not maximum throughput - set the ack-value to 1. Ack-value 1 can be seen as an intermediate between both of the above.

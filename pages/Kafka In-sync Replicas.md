---
title: Kafka In-sync Replicas
---

- Kafka considers that a record is committed when all replicas in the In-Sync Replica set (ISR) have confirmed that they have written the record to disk.

- [[ACK]]

- What is the ISR?
	 - The ISR is simply all the replicas of a partition that are "in-sync" with the leader. The definition of "in-sync" depends on the topic configuration, but by default, it means that a replica is or has been fully caught up with the leader in the last 10 seconds. The setting for this time period is: replica.lag.time.max.ms and has a server default which can be overridden on a per topic basis.

	 - At a minimum the, ISR will consist of the leader replica and any additional follower replicas that are also considered in-sync. Followers replicate data from the leader to themselves by sending Fetch Requests periodically, by default every 500ms.

	 - If a follower fails, then it will cease sending fetch requests and after the default, 10 seconds will be removed from the ISR. Likewise, if a follower slows down, perhaps a network related issue or constrained server resources, then as soon as it has been lagging behind the leader for more than 10 seconds it is removed from the ISR.

- what is ISR for?
	 - The ISR acts as a trade-off between safety and latency. As a producer, if we really didn't want to lose a message, we'd make sure that the message has been replicated to all replicas before receiving an acknowledgement. But this is problematic as the loss or slowdown of a single replica could cause a partition to become unavailable or add extremely high latencies. So the goal is to be able to tolerate one or more replicas being lost or being very slow.

	 - When a producer uses the "all" value for the acks setting. It is saying: only give me an acknowledgment once all in-sync replicas have the message. If a replica has failed or is being really slow, it will not be part of the ISR and will not cause unavailability or high latency, and we still, normally, get redundancy of our message.

	 - So the ISR exists to balance safety with availability and latency. But it does have one surprising Achilles heel. If all followers are going slow, then the ISR might only consist of the leader. So an acks=all message might get acknowledged when only a single replica (the leader) has it. This leaves the message vulnerable to being lost. This is where the min-insync.replicas broker/topic configuration helps. If it is set it to 2 for example, then if the ISR does shrink to one replica, then the incoming messages are rejected. It acts as a safety measure for when we care deeply about avoiding message loss.

- The minimum number of in-sync replicas has nothing to do with the throughput. Setting the minimum number of in-sync replicas to larger than 1 may ensure less or no data loss, but throughput varies depending on the ack value configuration.

- Default minimum in-sync replicas are set to 1 by default in CloudKarafka. This means that the minimum number of in-sync replicas that must be available for the producer to successfully send records to a partition must be 1.

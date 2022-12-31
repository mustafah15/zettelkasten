---
title: Partition Tolerance
---

- Partition Tolerance In Distributed Systems
id:: dec4a568-66ee-4277-a8c0-ac86e9e4fb6e
	 - **Definition**: the system continue to operate despite an arbitrary number of messages being dropped or delayed by the network.
id:: 975373e6-d15b-4948-ad15-63d13047121e

	 - so the reality is no distributed system is safe from the partition, they can occur due to problems in the network, or just node can go down for one reason or another. so in any of those partition cases we have an interruption in our system communication, these interruption can be short or long-lived. 
id:: c9a0b791-d98a-4fec-9948-2b8a24fc4707

	 - [[CAP Theorem]] has more information how to a distributed system should deal with the partitions. 
id:: 47677200-25e6-43d9-8792-838cc010a64d

---
title: Kafka High-Water Mark
---

- The **high watermark offset** is the offset of the last message that was successfully copied to all of the log’s replicas.

- To ensure data consistency, the leader broker never returns (or exposes) messages which have not been replicated to a minimum set of ISRs. For this, brokers keep track of the high-water mark, which is the highest offset that all ISRs of a particular partition share. The leader exposes data only up to the high-water mark offset and propagates the high-water mark offset to all followers. Let’s understand this with an example.

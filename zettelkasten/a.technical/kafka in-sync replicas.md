---
tags:
  - system-design
  - distributed-systems
related: "[[kafka]]"
type: permanent
---
Kafka considers that a record is committed when all replicas in the [[in-sync replica set]] have confirmed that hey have written the record to disk.

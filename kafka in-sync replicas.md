---
tags:
  - system-design
  - distributed-systems
type:
  - literature
related: "[[kafka]]"
---
Kafka considers that a record is committed when all replicas in the [[in-sync replica set]] have confirmed that hey have written the record to disk.

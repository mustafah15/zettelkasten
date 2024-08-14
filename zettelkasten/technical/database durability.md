---
tags:
  - database
related: "[[database engineering]]"
type:
  - fleeting
---
- the process of ensuring persisting transaction permanently and do not accidentally disappear or get erased even during a database crash.
- durability actions are slow because to make things durable that means you write to disk and writing to the disk is slow.
- this means changes made by committed transactions must be persisted in a durable non-volatile storage.
- most of DBMSs bypass the os cache to ensure durability by fsync os which can be expensive and slow down commits.

related:
- [[database durability techniques]]

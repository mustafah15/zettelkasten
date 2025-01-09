---
tags:
  - database
parent: "[[database read phenomenas]]"
aliases:
  - phantom reads
type: permanent
deeper: "[[how to avoid database phantom reads]]"
folgezettel: 3a2g4c
---
A phantom read **occurs when a transaction retrieves a set of rows twice and new rows are inserted into or removed from that set by another transaction that is committed in between**.

---
title: Commit Log
---

- A commit log is a record of transactions. It's used to keep track of what's happening, and help with e.g. disaster recovery - generally, all commits are written to the log before being applied, so transactions that were in flight when the server went down can be recovered and re-applied by checking the log.

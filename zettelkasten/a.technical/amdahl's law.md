---
tags:
  - software-design
  - distributed-systems
parent: "[[contention in distributed systems]]"
related: "[[gunther's universal law]]"
type: permanent
---


- The low defines the maximum improvements gained by parallel processing. Improvements from parallel processing are limited to the code that can be parallelized so if you have pieces of code that can be parallelized you can improve those, the pieces that can't be parallelized there's nothing you can do about it and that lead to resource contention. contention limits parallelization and their fore reduce the improvements.
- so as we see in this graph increasing speed (throughput) can be done by adding more concurrency jobs until reach some point and after that limit, it becomes useless if you add more parallelization the improvements there will be barely noticeable
- but in an ideal world (fantasy) we would have [[linear scalability]] if we add more processors that work in parallel (concurrency) which should lead to more speed (throughput)
- ![[Pasted image 20230903095851.png]]
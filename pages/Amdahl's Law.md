---
title: Amdahl's Law
---

- Amdahl's Law
  id:: 6a99938c-f265-45ac-b89f-0dafa71e04e0
	- ![](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ea/AmdahlsLaw.svg/1200px-AmdahlsLaw.svg.png)
	  id:: 65142209-3d2c-4409-bdb8-da3f41055b80
	- The low defines the maximum improvements gained by parallel processing. Improvements from parallel processing are limited to the code that can be parallelized so if you have pieces of code that can be parallelized you can improve those, the pieces that can't be parallelized there's nothing you can do about it and that lead to resource contention. contention limits parallelization and their fore reduce the improvements.
	  id:: a7ae6e7a-db20-4ab2-9e8e-e787be3706f2
	- so as we see in this graph increasing speed (throughput) can be done by adding more concurrency jobs until reach some point and after that limit, it becomes useless if you add more parallelization the improvements there will be barely noticeable 
	  id:: ef542c7d-be9d-44d5-976f-40fce005230a
	- but in an ideal world (fantasy) we would have [[linear scalability]] if we add more processors that work in parallel (concurrency) which should lead to more speed (throughput)
	  id:: bc90878a-d636-46b3-8b8e-304de669abfc
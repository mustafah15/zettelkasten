---
tags:
  - distributed-systems
  - system-design
type:
  - literature
---


tags: #distributed-systems #software-design 
type: #literature 

----
 what is scalability definition?
	- **a system called scalable if it can meet increases in demand while remaining responsive.**
	- a system may have to scale because of many reasons like increased data volume or increased amount of work, e.g., number of transactions. a scalable system would like to achieve scaling without performance loss.
[[horizontal scaling]] horizontal scaling means that you scale by adding more servers into your pool of resources
[[vertical scaling]] means that you scale by adding more power (CPU, RAM, Storage, etc.) to an existing server.
horizontal-scaling is **often easier** to scale dynamically by adding more machines into the existing pool; Vertical-scaling is usually limited to the capacity of a single server and scaling beyond that capacity often involves downtime and comes with an upper limit.

followed up with:
- #### [[scalability vs performance]]
- #### [[contention in distributed systems]]

---
title: Caching
---

- Caching will enable you to make vastly better use of the resources you have as well as making other wise unattainable product requirements feasible. caches take advantage of the locality of reference principle recently requested data is likely to be requested again. A cache is like short-term memory: it has a limited amount of space, but is typically faster than the original data source and contains the most recently accessed items.

- [[Application server cache]]
	 - Placing a cache directly on a request layer node enables that local storage of response data. Each time a request is made to the service the node will quickly return local cached data if it exists. if it is not in the cache, the requesting node will query the data from the disk.

	 - what happens when you expand this to many nodes? if the request layer is expanded to multiple nodes, it's still quite possible to have each node host its own cache. however if your load balancer randomly distributes requests across the nodes the same request will go to different nodes, thus increasing cache misses. two choices for overcoming this hurdle are **global caches** and **distributed caches**.

- [[Cache Invalidation]]
	 - while caching is fantastic it doses require some maintenance for keeping cache coherent with the source of truth (database). if the data is modified in the database, it should be invalidated in the cache; if not this can cause inconsistent application behavior.

	 - there are three main schemas that are used for solving this problem
		 - **Write through cache**: under this schema, data is written into the cache and the corresponding database at the same time. the cached data allows for the fast retrieval and, since the same data gets written in the permanent storage, we will have complete data consistency between the cache and the storage.

		 - **Write around cache**: This technique is similar to write through cache but data is **written directly to permanent storage, bypassing the cache**. this can reduce the cache being flooded with write operation that will but subsequently be re-read, but has the disadvantage that a read request for recently written data will create a "cache miss" and must be read from slower backend storage and experience higher latency.

		 - **write-back cache**: under this schema, data is written to cache alone and completion is immediately confirmed to the client the write to the permanent storage is done after specified intervals or under certain conditions. this results in low latency and hight throughput for write intensive application, however this speed comes with the risk of data loss in case of crash or other adverse event because the only copy of the written data is in the cache.

- [[Cache eviction Polices]]
	 - following are some of the most common cache eviction policies:
		 - **First In First Out:** the cache evicts the first block accessed first without any regard how often or how many times it was accessed before.

		 - **Last In First Out:** The cache evicts the block accessed most recently without any regard to how often or how many times it was accessed before

		 - **Least Recently Used:** Discards the least recently used first.

		 - **Most Recently Used:** Discards the most recently used items first.

		 - **Least Frequently Used:** Count how often an item is needed those that are used least often are discarded first.

		 - **Random Replacement**: Randomly selects a candidate item and discards it to make space when necessary.

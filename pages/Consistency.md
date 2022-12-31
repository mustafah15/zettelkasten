---
title: Consistency
---

- consistency in distributed systems
id:: af7b81ab-906d-4631-b2b8-6350c03d0675
	 - distributed systems by definition are separated by space there's a limit on information speed, it takes time to transfer the information, the state of the original sender may have changed, This means the receiver of the information is always dealing with stale data.
id:: f1c70cb8-f3f0-40e3-aeb9-a7e719a3cb29

	 - [[eventual consistency]]
id:: bf13e99c-dcd9-4929-b137-ffe1fdd1421f
		 - Eventual consistency garnets that **in absence of new updates, all access to a specific piece of data will eventually return the most recent value**. so in order to reach a state of consistency, you have to stop all updates at least for some period of time.
id:: 5a5e4a8f-e069-4753-9c49-f8bab56a4769

	 - [[strong consistency]]
id:: 57814f2a-f517-40fe-ba7e-41651f3b76c6
		 - Strong consistency garnets that **an update to a piece of data needs an agreement from all nodes before it becomes visible**. we can apply strong consistency by using a non distributed system as a lock to our data that lock has the data only and the whole distributed system read from it. that comes at a cost, It affects our availability to recline to be elastic as this becomes a point of contention in the system. **Traditional monolithic architecture** are usually based around strong consistency.
id:: b5c3ebe9-9f2c-438e-9638-3a76ebcfad59

		 - But how can we reach a strong consistency if physics tells us that we can't? so we usually do it by introducing techniques that simulate strong consistency **Locks** are examples of this, by taking a distributed system problem and reducing it to non distributed resource. so if we have different distributed services that communicate to a non distributed database where we have the lock and we have only one copy of it. because this database is not distributed we can eliminate distributed system problem that only exists when we have multiple services that are responsible for the same piece of data. so this can give us a strong consistent system. However, this comes with a cost as whenever we introduce a lock like this it comes with a cost of contention that might affect our ability to be elastic and resilient. we will discuss the effect of contention in the next part.
id:: 31367cb4-6e62-408b-9571-8882e813dc9e

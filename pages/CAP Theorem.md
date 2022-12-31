---
title: CAP Theorem
---

- CAP Theorem
id:: 3b608f82-764f-41e5-9b5d-cfc91f559e80
	 - we already mentioned the [[Laws Of Scalability]] that distributed systems have to deal with but there's another role that they have to pay attention to and that is something we call the cap theorem. Distributed systems must account for the cap theorem.
id:: 959cc824-6dfa-4e16-a5a2-2624ea2e1901

	 - CAP Theorem states that a distributed system can not provide more than two of the following Consistency, Availability, Partition Tolerance.
id:: 2255e22c-f74d-4323-8f8e-2cc8e8ad9610

	 - ![](https://cdn.educba.com/academy/wp-content/uploads/2020/01/CAP-Theorem-last.jpg)
id:: 0ba6a240-956b-431b-b886-7d1177eb8f3a

	 - so more explanation according to our diagram here if we want to move our system towards the CP side (consistency and partition tolerance) that means we have to move away from availability, as the more we move towards CP the more we have to sacrifice availability.
id:: 8401cae5-fe2e-4b26-95f4-9ddfda66813d

	 - similarly, if we want to move the other direction and go to the AP (availability, partition tolerance) side, by doing so we have to sacrifice consistency to do that. 
id:: 1b2444d1-8f9f-447e-b885-61815f24e0cc

	 - so that's the way CAP Theorem works is that we can only provide two of those guarantees at any given time we can't provide all three. But wait a second why we can't move towards CA side? the reality is the CA side is really not a valid choice. As we discussed in [[Partition Tolerance]] part there's no distributed system is safe from the partitions. 
id:: fc5ae066-8eca-4947-b3fa-0a42ef369ebb

	 - when partition occurs, a distributed system has two options
id:: 2955d53b-9ced-4f45-b5dc-8d7628da23b0
		 - **AP** sacrifice consistency allowing writes to both sides of partitions when partitions is resolved you will need to away to merge the data in order to restore consistency.
id:: c29c5e49-a3cf-44e7-a007-eacfe70c03fd

		 - **CP** sacrifice availability, disability or or terminating one side of the partition, during the partition some or all of your system will be unavailable.
id:: 45a69e20-fca0-4ab9-832a-17047b2a6260

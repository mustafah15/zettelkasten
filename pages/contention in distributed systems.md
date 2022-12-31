---
title: contention in distributed systems
---

- Effect of contention in distributed systems
id:: 9781671d-f9b5-4b6d-b863-c19298477a54
	 - what is contention?
id:: 1e13cf5d-bc4d-4655-b5b2-fe1276c3157d
		 - Any two requests that content for a single limited resource are in contention, this contention can only have one winner. other forced to wait for the winner to complete, as the number of things competing for increases the time to free up resources increases and eventually exceed acceptable time. As the number of things (requests) that competes for the resource increases the time to free up the resource increases. As the load increases, we will eventually exceed acceptable time limits.
id:: 1cc19217-e96d-48a9-8972-29ae1bee2ea8

	 - How contention effect scalability?
id:: 2c228411-5c4d-4cfe-8a7a-c511c1ec2b3e
		 - ((6a99938c-f265-45ac-b89f-0dafa71e04e0))
id:: fb623e00-c20e-4035-aebe-6ee16811adc2
			 - ((65142209-3d2c-4409-bdb8-da3f41055b80))
id:: 70bc03c4-8ac4-4d52-8c7e-5d123f6ca470

			 - ((a7ae6e7a-db20-4ab2-9e8e-e787be3706f2))
id:: 5e82730f-6abf-4568-91a3-5ce4998ff17f

			 - ((ef542c7d-be9d-44d5-976f-40fce005230a))
id:: 96a56d41-4133-423a-9760-e26d38dea8d7

			 - ((bc90878a-d636-46b3-8b8e-304de669abfc))
id:: 68bd0c6b-76e0-41fc-a68f-e31758696074

		 - As [[Amdahl's Law]] showed us the effect of contention on a distributed system and demonstrated that when we have contention as we try to add more parallelisation or as we try to scale up we start to see diminishing returns, there's another effect we have to take into account and that is [[the effect of coherency delay]]
id:: 9fc44c22-f826-47fc-8a3f-732e3241c639

		 - ((a87df8fb-d7f2-4b9a-b4c3-e938c5efb1be))
id:: 32c167c5-597c-4171-9092-ed3df04f5c17
			 - ((d195b407-ade0-4655-b8e9-21926a8d0000))
id:: 70dd133c-cbcd-42d5-b105-10b6a656bfe2

			 - ((462f0ab0-38d5-4b5e-b011-f6a3161c7a06))
id:: a0d87668-2e81-4494-ba20-25b2516dc7fd

		 - ((eaadda3d-3a3f-4c4c-824f-6164a18fbe53))
id:: 48fd3f3f-4f15-4ac4-b838-a7ebdbfb8e63
			 - ((0e27aec3-9217-46f9-a758-9bb0b0a6abc6))
id:: 57ecdde7-f910-4b3d-aa95-e2d0baabb8b5

			 - ((fdd50046-5677-46d0-b49b-915569c5d806))
id:: 9f9f78fd-61db-4a71-862f-55e6fc436ff9

		 - ((7febcdce-21cc-45a3-9686-8ece87594013))
id:: 074e0301-86eb-4efe-a56d-8d57f4fafb22
			 - ((2aa154b5-333e-40f1-80e1-a622fc9e2fd1))
id:: 6de5164c-b047-4fb4-9aef-2af858022800

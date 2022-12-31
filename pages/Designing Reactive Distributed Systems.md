---
title: Designing Reactive Distributed Systems
---

- These are my notes about the Designing reactive Distributed Systems organised in a way that I see it logical for me, if you want to use the same order that's okay but also feel free to skip to whatever part you find useful for you at that moment.

- But before we start we should know what is a distributed system.
	 - so **the definition** of a [[distributed system]] is a system with multiple components (nodes) located on different machines that communicate and coordinate actions in order to appear as a single system to the end-user.

	 - why we need to build a distributed systems in the first place?

	 - distributed systems have endless use cases, a few being electronic banking systems, massively multiplayer online games or a sensors network.

	 - another reason for building distributed systems is that some applications require high availability and need to be resilient to single node failures. some other applications need to tackle workloads that are just too big to fit a single node server, and it has to be scalable enough to handle such high traffic and load, like Google or Facebook where they receive hundreds of thousands of requests per second from all over the globe.

	 - in this book, we will take a deep look into the main challenges that will face you during designing, building your distributed systems: [[Communication and Coordination]], [[Scalability]] and [[Partition Tolerance]]. we will discuss what are the best approaches from the reactive architecture point of view.

- [[Types Of Distributed Systems Architectures]] 
	 - ((1bb7e6c4-9e73-44e5-882d-435ecb0ee12c))
		 - ((34afca3c-62da-48eb-a5db-6509b8b3d86f))

		 - ((c07aa6cb-8256-43a2-b59a-cef54525904d))
			 - ((aa3b3b65-a81b-4387-b539-81ad50893143))

		 - ((ffba0050-ce41-4c75-9cd4-5b5a1a513c57))
			 - ((9025fbdd-9f0e-43a8-a525-699c8e3196d6))

		 - ((fc5b89d5-d077-4e4d-9c83-494cb6bae16a))
			 - ((edf8d776-3c22-4dcd-b772-992d6c1e4741))

		 - ((c25f5ed2-dcaa-40c3-9140-5bace126998c))
			 - ((ed4218de-d488-4f21-8819-5384e350daba))

		 - ((c6dab3ec-f095-48aa-8ea2-31b067b21ad1))

- [[The Key Characteristics Of Distributed Systems]]
	 - ((015bf8b9-8804-48c0-9242-c412885d01d4))
		 - ((73373e7e-4a83-454f-b386-574c47e33606))
			 - ((633c191f-2497-4af9-80d6-7620ee712af0))
				 - ((2f6eb8f1-2675-4646-a9e4-902a2a259ffa))

				 - ((3843d9f1-5d63-49ad-8363-38e8c3f99a13))
					 - ((6f1c3b41-f582-47a3-9530-e0a09c87a060))

				 - ((dbcd6170-c1c2-45d2-98bb-bb28dac17061))
					 - ((548db675-73fb-4bf3-9e34-3b68aa5f27fd))

					 - ((18f5e5b3-7150-4492-bd80-9602903f160f))

		 - ((ba62bd0b-a844-47d5-b170-8953916289d2))
			 - ((22c6ed98-8981-4cd6-96bc-617499b5f76c))
				 - ((1b8e8efb-3ae3-4769-8e18-8dc36b5a3e37))
					 - ((3e26864e-eec3-48c9-8b69-c0461417a311))

					 - ((9f226f8e-0d8a-4964-9fa3-d65130137132))

				 - ((e91707f7-19a5-4c90-9fd1-e0408cd7bbf3))

				 - ((20a3abdf-5314-4b25-a331-2bff1086f38c))

				 - ((2ae2120f-0859-43f5-bbcb-e7856067a1c9))

				 - ((2a4d3f2e-7e75-4f65-812a-9e981f03721e))
					 - ((c0979aac-20f3-4379-b9d6-e076f7425cce))
						 - ((3db39aa1-a2b8-409b-9473-b3f2da101cbf))

						 - ((cb008b1c-6013-436f-a324-f88f5e905764))

						 - ((bbd94bd4-3e45-4b5c-84c8-cb06a7c0d1a9))

						 - ((17d4814d-d3df-4941-aa40-b655315a9833))
							 - ((c66f8443-68ef-4eb6-97b1-0138f107af7f))

							 - ((fc1d94a6-68ab-4652-a7cc-58abec5b0bea))

						 - ((39b5fb38-e088-45f8-a2a9-e5fd92df4a1a))
							 - ((4c45af4e-6134-4ff5-b8f5-8bc09fe5f8a8))

							 - ((bb4ac0eb-1b54-4bc0-9f5e-378abb4dedce))

				 - ((98074087-9794-4b95-b1df-0c16a33090d7))
					 - ((55105551-cf61-43e6-851c-b3a172ef483b))
						 - ((849edb3d-fc85-4a9a-b87d-c18495fa8e76))
							 - ((a0fdb7f5-dca7-4028-bd01-32904cc084b5))

						 - ((171cdd5a-f1b7-469f-a188-7f669ffe320b))
							 - ((6a8bd058-c30d-40d2-90ee-4f08c9384f48))
								 - ((41452308-9765-48a0-90b6-9f7dc142179c))

								 - ((af3754e8-302f-41cd-8719-d65dc84e42aa))

								 - ((0f129c0d-58b3-46c4-a651-6a6682113142))

								 - ((93a6994d-7652-43fd-8219-e7dc88c4bcb0))

							 - ((01aa5b5c-d7d7-494b-83ac-7aed84769df4))

							 - ((e5e05700-648a-4d23-84a2-92f86a4bfa30))
								 - ((7b572382-5677-4043-8cba-ac9205143192))

								 - ((9a7c14e8-1a5b-46e3-8e2f-a38cd4a6805b))

							 - ((1d27c077-0361-4fe8-aee7-60ef78045cb8))
								 - ((a16ecf5b-5967-47a9-afa3-43459705de07))

								 - ((1332a818-2df3-4bb3-b0a1-4a1826889160))

							 - ((9ed51727-d9a2-468c-ac36-6f919e4290ed))
								 - ((589a0887-07ad-4542-bbfc-734cbebd34a1))

		 - ((c07e2d75-b5b8-4b95-a427-1b93f69642b2))
			 - ((b851edec-4e5e-4092-ae0f-b4c8bf6b6b59))
				 - ((e27a59aa-c83f-42c5-b045-ca84749684b9))
					 - ((f717cc20-1f0f-40ea-b3eb-1def8ca9a183))

				 - ((16543fb2-31b5-4eda-9768-2124e6736e8e))
					 - ((c6bda4a3-24d5-4842-b596-cb7e8a59a91a))

				 - ((7cd473e2-d12f-4c07-b63c-58e4fbdf2f27))
					 - ((34955428-f49c-4426-bb4c-3142db39c6ca))

		 - ((c31f8fcb-6f87-49cc-9bb4-2444266f5bef))
			 - ((f0d4dc93-f535-40f1-bf72-2ee4ac0471e7))
				 - ((cce71ead-52f2-4abb-99bb-2aac9ae4f19e))

				 - ((4df43903-c952-403c-8dcc-f6e829f8d11d))

				 - ((328490bf-4bd2-490d-8be4-645a36d1b096))

- [[CAP Theorem]]
	 - ((3b608f82-764f-41e5-9b5d-cfc91f559e80))
		 - ((959cc824-6dfa-4e16-a5a2-2624ea2e1901))

		 - ((2255e22c-f74d-4323-8f8e-2cc8e8ad9610))

		 - ((0ba6a240-956b-431b-b886-7d1177eb8f3a))

		 - ((8401cae5-fe2e-4b26-95f4-9ddfda66813d))

		 - ((1b2444d1-8f9f-447e-b885-61815f24e0cc))

		 - ((fc5ae066-8eca-4947-b3fa-0a42ef369ebb))

		 - ((2955d53b-9ced-4f45-b5dc-8d7628da23b0))
			 - ((c29c5e49-a3cf-44e7-a007-eacfe70c03fd))

			 - ((45a69e20-fca0-4ab9-832a-17047b2a6260))

		 - ((75bcd897-6707-49bd-bb86-94905e56a489))
			 - ((e18d28a1-e49b-4a74-9531-44dc34fd3202))

			 - ((34550340-0893-44bd-9da4-f20746281a9a))

- [[Reactive Distributed Systems]]
	 - ((de4d3f88-7316-44b7-b9ee-5023ce025746))
		 - ((d9430d53-117c-4bd3-b197-e7280bd68333))

		 - ((3c7dbfde-a189-4765-834c-2829f3e07209))
			 - ((91a8b32d-039d-4d3a-8e34-7d0da9f21090))
				 - ((e716ed59-c951-4cbe-bc10-2a5de7cf7be2))

				 - ((6d2e10bd-884b-42c1-afd3-2c49291e7f99))

				 - ((4ac86e23-b213-4756-a0d8-d3296feeceac))

		 - ((f7d800f6-42a0-452f-85ed-246e0ff0e249))
			 - ((8369ae44-3e79-4b01-80c5-47614466bc20))
				 - ((e18cf17e-a770-4477-9932-b5625ad12284))

				 - ((ab12b48b-678d-4916-805a-f759bffca7c9))

		 - ((b553a202-2296-45d0-951b-1e296c7eec9b))
			 - ((97cfc0ff-72db-4b22-8996-38fda66fa911))
				 - ((1c625934-facd-4abe-85c9-fe975ff496a2))

				 - ((6a3e797d-7f70-4526-b3bf-533fb92c7e12))
					 - ((eee60f4b-82b8-47df-b939-b2b6e32462fd))

					 - ((d39b06cb-5b6d-4f58-b621-918edade7b74))

				 - ((20597ab9-0ae6-4282-b451-98156ecb6a14))
					 - ((3e812a74-8c5d-4134-9983-0dd5be915aab))

					 - ((3f433edc-9874-4b8a-bbb2-a819d720737a))

				 - ((2c10fc6d-501f-482a-8403-7ff34a61b73f))
					 - ((a5862d3d-e687-4300-9773-6bed6aa9d750))

					 - ((70239c99-8f77-487b-bd12-8eb1efcf95d9))

					 - ((a852122b-b64c-476a-a2b9-50fa1c70410b))

				 - ((a4c71400-615e-41b7-a9a6-765956638f3a))
					 - ((e39feec3-dcf1-4cc0-b9a2-38546e1dc123))

					 - ((c9c77139-7b68-4ab3-9e9a-f73ca4920c94))

					 - ((029fddcd-c84f-4a08-b9f3-303c585a515a))

		 - ((f7a2f735-e972-4dd4-80fe-17df1c68951d))

- SCALABILITY
	 - [[Reactive Microservices]]
		 - [[Domain Driven Design]]

	 - [[microservices vs distributed monolith]]

	 - [[Load Balancing]]

- COMMUNICATION
	 - [[Communication and Coordination]] 
		 - [[sync communication ]]
			 - [[Remote procedure calls]]

			 - [[REST]]

		 - [[async communication]] 
			 - [[message communication]] 

			 - [[multicast communication]]

		 - [[Messaging Patterns]]
			 - [[Point to Point messaging]]

			 - [[Publish Subscribe messaging]]

		 - [[Failure detection]]

		 - [[Time & Clocks]]

		 - [[Transactions]]
			 - [[ACID]]

			 - [[Asynchronous Transactions]]
				 - [[Saga Pattern]]

		 - [[Redundancy and Replication]]
			 - [[conflict free replicated data types]] 

			 - [[Caching]]

		 - [[event sourcing]] and [[CQRS]]

- PARTITON TOLERENCE
	 - [[Resiliency]] 
		 - [[Circuit Breaker]]

		 - [[Bulkhead]]

		 - [[Byzantine fault]]

- monitoring 
	 - [[golden metrics for monitoring]]

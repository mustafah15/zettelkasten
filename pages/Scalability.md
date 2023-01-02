---
title: Scalability
---

- scalability in distributed systems
  id:: a345c836-cd09-4de0-8ae6-068893274534
	- what is scalability definition? 
	  id:: b5091483-d65a-4f8f-82a4-75edb26f2a4d
		- **a system called scalable if it can meet increases in demand while remaining responsive.**
		  id:: 300585ed-fb09-4294-a107-9632cf53195c
		- a system may have to scale because of many reasons like increased data volume or increased amount of work, e.g., number of transactions. a scalable system would like to achieve scaling without performance loss.
		  id:: da7eece8-592b-459e-b7b4-35143c052761
	- [[horizontal scaling]] means that you scale by adding more servers into your pool of resources
	  id:: 0284bf1a-94b3-4e15-ac67-3392a91631ca
	- [[vertical scaling]] means that you scale by adding more power (CPU, RAM, Storage, etc.) to an existing server.
	  id:: 65dbc68c-d17a-4aaa-bf49-834e5f7e90e7
	- horizontal-scaling is **often easier** to scale dynamically by adding more machines into the existing pool; Vertical-scaling is usually limited to the capacity of a single server and scaling beyond that capacity often involves downtime and comes with an upper limit.
	  id:: eeb67d52-52f1-4fda-b43c-2ce7fdbe79fc
	- [[scalability vs performance]] 
	  id:: 2f9b1746-33ed-49d7-b1f6-d5ab40884a6c
	  collapsed:: true
		- ((f7eced76-e757-446e-ad78-9bb5f7b422e7))
		  id:: d3a0942f-3af2-47a4-8758-7e0b0b1a515d
			- ((192bedca-35dd-4e3a-9a92-5244206127e6))
			  id:: f87261ad-e5e6-48ce-b8fa-3d9edf24b85a
			- ((0c020ce0-74f3-49a6-842d-a2f81e58bbea))
			  id:: fa259fed-36cb-40e3-8129-9ab0126ff0b7
			- ((4d0167c6-b742-45a2-98ca-e48a4d1fff80))
			  id:: 8399be4d-6ccd-486d-8961-c95c87455c49
			- ((08e0234f-85d5-441e-8359-a0d5e5ec7b47))
			  id:: 488832da-9506-472d-b5a6-5a0722b0e252
				- ((2b486c30-595b-41cf-8a90-024b25358578))
				  id:: 86ac8f2e-d2d0-41e7-ab16-11d0d4e3f923
				- ((1c12508c-c109-4dd6-9c9c-a6c5153cda2e))
				  id:: d3f519c8-0b5a-48ad-909e-a505bd4a5f15
			- ((7b8e8e23-f19c-49eb-9ac9-cf2226d0b709))
			  id:: d0156312-a8e8-45c1-a0eb-5566995f5b16
				- ((bc11e177-76e6-44fa-8ebc-7df9aa6085f4))
				  id:: f251cf05-f5ec-49a7-b9e6-c39effe79ea0
				- ((c21d8187-38a5-48ca-8f27-c276245ba090))
				  id:: 86f6e5a5-001d-40e7-bcb1-6667f0253952
	- [[contention in distributed systems]]
	  id:: a8c8a0a5-3c54-4e3b-8177-45da792078ab
	  collapsed:: true
		- ((9781671d-f9b5-4b6d-b863-c19298477a54))
		  id:: f61944d3-14b6-4795-86b7-e657b043f942
			- ((1e13cf5d-bc4d-4655-b5b2-fe1276c3157d))
			  id:: ebe020dc-c4f9-45d4-9007-860a63b4be29
				- ((1cc19217-e96d-48a9-8972-29ae1bee2ea8))
				  id:: 14ffbad8-b205-413c-97bb-40fa2849a465
			- ((2c228411-5c4d-4cfe-8a7a-c511c1ec2b3e))
			  id:: 4f9911e1-e3e7-4d02-ab0e-e0b486cb77fc
				- ((fb623e00-c20e-4035-aebe-6ee16811adc2))
				  id:: 587ccc9f-9e9a-4e43-a1c1-b988f9261467
					- ((70bc03c4-8ac4-4d52-8c7e-5d123f6ca470))
					  id:: 62622929-9f89-4b53-b315-4b7ca354f9df
					- ((5e82730f-6abf-4568-91a3-5ce4998ff17f))
					  id:: a060808a-a78c-494e-8492-172135da8a50
					- ((96a56d41-4133-423a-9760-e26d38dea8d7))
					  id:: d383ef0e-ecd7-45ba-ab39-d8d7ca4fef57
					- ((68bd0c6b-76e0-41fc-a68f-e31758696074))
					  id:: 580a55a2-da45-4b08-a6a7-ba336bed30cd
				- ((9fc44c22-f826-47fc-8a3f-732e3241c639))
				  id:: 4ef0744f-ae40-4bf1-914a-aed2d230f347
				- ((32c167c5-597c-4171-9092-ed3df04f5c17))
				  id:: 1e05609d-2259-47ba-9a99-d808197b7e3a
					- ((70dd133c-cbcd-42d5-b105-10b6a656bfe2))
					  id:: 75353142-465f-450f-b96c-94536b945dab
					- ((a0d87668-2e81-4494-ba20-25b2516dc7fd))
					  id:: d8bf612b-4831-4fbc-9f57-aefe53fac3d1
				- ((48fd3f3f-4f15-4ac4-b838-a7ebdbfb8e63))
				  id:: 5b9df288-1e93-42a7-ad35-8d74f98c7db9
					- ((57ecdde7-f910-4b3d-aa95-e2d0baabb8b5))
					  id:: 0d266bbb-069f-49ab-afc3-43c45732f192
					- ((9f9f78fd-61db-4a71-862f-55e6fc436ff9))
					  id:: 6cd214da-7bd0-45d4-891a-67aa9d4be46e
				- ((074e0301-86eb-4efe-a56d-8d57f4fafb22))
				  id:: 8df1840c-993c-4a64-9e17-c24d7f4578d5
					- ((6de5164c-b047-4fb4-9aef-2af858022800))
					  id:: 25cd2605-0826-4fdf-9ac7-defe9187245e
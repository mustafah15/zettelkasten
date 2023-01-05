---
title: philosophy of software design/complexity in software design
---

-
- Complexity In Software Design
  id:: 43b5d9f4-1904-49f8-af0f-55cafa6b02ba
	- Complexity Definition
		- Complexity is anything related to the structure of a software system makes it hard to understand and modify the system.
	- It's all about complexity
		- The greatest limitation in on writing software is our ability to understand the system we are creating and since the programs we write evolve and acquire more features. it become complicated with tangled dependencies between it's components
		- overtime complexity accumulates and it becomes harder and harder for developers to keep all relevant factors in mind as they modify the system.
		  id:: 63851b23-9af0-4c5f-9f49-086818192fb8
		- Because of software is so malleable. software design is a continues process that span the entire life cycle of a software system this make software design different from the design of the physical systems such as building ships...etc
		- however software design has not always been viewed like this for much of the history of programming, design was constructed at the beginning of a project this was called waterfall model. in this [[waterfall model]] each phase completed before the next phase starts.
		- waterfall model rarely works well for software system, software system are more complicated than the physical systems it's not possible to visualize the design of large software system well enough to understand all of it's implications before building anything.
		- as a result the initial design will have many problems the problems do not become apparent until implementation is well underway. however the waterfall is not structured to accommodate major design changes at this point. because of this most of software development projects today use all incremental approaches such as [[agile development]] in which the initial design focuses on small subset of the overall functionalities.
		- incremental development means that software design is never done. design happens continuously over the life of system as software developers should always be thinking about the design issues.
		- to improve the design of the system you are working on and should spend some time on design improvements
		- the best way to use this book is in conjunction with code reviews. when you read other people code it's easier to see design problems in someone else's code than your own. you can use red flags described here to identify problems and suggested improvements.
	- Two general approaches to fighting complexity
		- eliminate complexity by making code simpler and more obvious.
			- for example complexity can be reduced by eliminating special cases or using identifiers in a function.
		- second approach is to encapsulate it
			- so programmer can work on a system without being exposed to all of it's complexity at once. this approach called [[modular design]]
	- complexity can take many forms. for example it might be hard to understand how a new piece of code works it might take a lot of effort to implement a small improvement, you also can think of a complexity in terms of cost and benefit. in complex systems it takes a lot of work to implement even small improvements in a simple system larger improvements can be implemented with less effort.
	  id:: d25e29be-673e-4032-9e75-d6b5a9975a10
	- the overall complexity of a system is determined by the complexity of each part (p) weighted by the fraction of time developers spend working on that part 
	  id:: 7e3c684f-2717-44bd-969c-5ce335ae21cb
		- c = C cp tp
		  id:: cf0ded2e-baa7-47d7-bebd-8e0a2b6efeb3
	- Complexity is more apparent to reader than writers. if you write a piece of code and it seems simple to you but other people think it is complex. then it's complex. when you find yourself in situations like this, it's worth probing the other developers to find out why the code seems complex to them; there are probably some interesting lessons to learn from the disconnect between your opinion and theirs. your job as developer is not just to create code that you can work with easily but to create code that others can work with easily 
	  id:: bf1b7b48-1de6-4e90-9e5a-7beec1bd21a4
	- [[symptoms of complexity]]
	  id:: ad2e5012-0423-4f5e-b6d6-eb36d594f450
		- ((932e6aec-8905-40ef-9ffc-c1e46d1ea4c9))
		  id:: 76584dca-860f-46ee-842f-d2d47be7db9e
			- ((b453841a-faeb-4f9d-850b-88b39358b0a7))
			  id:: 2efdda76-1e8b-4b42-841b-8c19226be3ef
				- ((35c166ad-8c17-4fd6-928c-03839c36ba82))
				  id:: 0722486b-8fd1-43c3-b8ea-367b0e85047e
			- ((4be21345-af6f-4c9e-aedd-878aaacc5eb2))
			  id:: 446db2b2-9aef-44f6-b890-a8ada423f259
				- ((6ba366d2-a2c0-48de-8423-ccb2ba05cb52))
				  id:: 36d90017-e135-48d2-8654-21a9bc2f6f58
				- ((f93c84b7-2e97-443f-a97f-c77f3cd1214c))
				  id:: 2b5c14bf-c44f-485a-bb06-ee6fef8e7dcc
				- ((e7307ede-2fd1-4748-bc11-c77a198d46b8))
				  id:: 1bbba260-96d2-48a6-9907-b1e073721bea
			- ((27085202-6c61-4fb2-8598-9c9d38de228b))
			  id:: 4b977dae-b7b2-4320-a558-2e090610363e
				- ((1318cd47-7182-405f-8f79-10ffc0474298))
				  id:: a9a693d6-b243-4121-a5f4-f7a17dbec775
				- ((c8c0511d-3448-4655-9753-bb693750d106))
				  id:: ebf9a6b5-e652-4420-ba53-c6a2a9c52622
				- ((d3ab3028-cf10-4e27-bfcb-f726485e49fb))
				  id:: 74b33e91-9b34-4b7c-9451-2b1875691d60
	- [[causes of complexity]]
	  id:: 8c8d13f3-0c36-4e04-9daa-5396a5dbe01a
		- ((6f938c1a-90c8-4e27-afcb-53058415bcee))
		  id:: 5f351c67-b103-4858-a7f9-3b6a6b12999f
			- ((8ca02e7c-c028-4db6-8a80-3d357ece46d8))
			  id:: f2f1b5c7-2b24-4370-ac34-a4ee75c49780
			- ((ee3d7684-266a-496b-9b5a-7c0bc84fbfba))
			  id:: a7476a8b-453a-49bd-aaf3-e624e31ba111
				- ((a750cd60-19fa-413e-98e3-7dab2cfc4aa7))
				  id:: 1a73aa58-96d4-4329-961a-27bfdcfe2e03
					- ((944bfa60-4a35-4aff-ba3f-78ed4f351632))
					  id:: 6edefd64-8397-41c3-b345-499f61927584
						- ((fc32939c-c9db-4fdd-b6c4-e8f5bb20f8f5))
						  id:: d2219c4d-6c3a-4a29-80c0-4627b4ea9224
						- ((fc66d06c-22f8-42fc-842e-17840ea0121f))
						  id:: d900977e-183f-48ae-a560-e2ed4043dbe7
				- ((212e1fb5-5484-47f8-a15e-447644a12025))
				  id:: 9567266b-fa69-4fd6-b044-59a6b5939dd1
					- ((efc4a287-a5a7-4d23-acd8-409b05607394))
					  id:: 10d02d95-cf46-4eef-8b22-610e9d029c12
						- ((0eed3071-e30d-4907-8afc-75cca0976ba9))
						  id:: b5c0fbb8-2e07-4460-9a1b-20323da93425
						- ((cdc273f2-ec5c-49ba-b972-796f35d7eaee))
						  id:: 439dacf5-c8e7-4112-86ca-2ca0e7a87e7a
						- ((86013f98-bd0f-47bc-97f2-eee3ce27b8a1))
						  id:: f14b3306-1805-4ff7-95b8-b70618f11a85
					- ((56200fb5-20ef-48a5-af2e-e3615c151585))
					  id:: 809b12be-064c-40c7-86e8-6303aebe34f2
	- [[complexity is incremental]]
	  id:: a09e8ad6-c5ed-4215-9b37-5624d5138e91
		- ((2fc92080-114d-4acc-8947-d5e07e6d667e))
		  id:: b852d85b-03e5-44a7-87ec-c819f1050490
			- ((7ddcc108-d87d-428e-9f2f-7d29d3e7815a))
			  id:: ff5b1913-3529-4961-ba30-799ace8c951f
			- ((734d30c7-cf5a-4256-9d86-d4f2979f193c))
			  id:: 03104c79-ba1b-4536-b0c8-660564746aa7
		- id:: f918c8ca-36f9-4a51-b134-ae40cc5958a6
---
title: shallow modules
---

- Shallow Modules
id:: 3009fdef-6d28-4ffb-ab42-baf67816e1a2
	 - a shallow module is one with a relatively complex interface, but not much functionality it dose not hide much complexity.
id:: 77b37dd4-eec6-4496-b385-e261ad9128af

	 - for example, a class that implements linked lists is shallow. it doesn't take much code to manipulate linked lists so the linked list abstraction doesn't hide very many details the complexity of a linked list interface is nearly as great as the complexity of its implementation. shallow classes are sometimes unavoidable, but they don't provide help much in managing complexity. 
id:: 61712076-d82a-438d-bb6e-cc3b004fa277

	 - #[[software design red flags]] 
id:: f81e0671-6587-48e1-b697-64804742499d
		 - shallow  module is one whose interface is  complicated relative to the functionality it provides shallow modules don't help much in the battle against complexity because the benefit they provide is negated by the cost of learning and using their interfaces. 
id:: aab9859e-042c-43a8-a819-7c7bc16a9415

---
title: Composite pattern
---

- What is the composite pattern?
id:: 8225045e-3fd5-478b-b161-cab802a763ff
	 - The composite pattern is used to structure objects in a tree-like hierarchy. Here, each node of the tree can be composed of either child node(s) or be a leaf (no children objects). This pattern allows the client to work with these components uniformly, that is, a single object can be treated exactly how a group of objects is treated.
id:: ff911cdd-2974-4f60-bdab-70541e36f339

	 - This pattern allows the formation of deeply-nested structures. If a __leaf__ object receives the request sent by the client, it will handle it. However, if the recipient is composed of children, the request is forwarded to the child components.
id:: c4a2ab5f-6d43-4ef7-850c-f413b374e3f5

	 - you can see that a composite pattern consists of the following:
id:: d4421b9a-5d59-46f2-bb8a-b53fdf9a3b2f
		 - **Component:** an abstract class that contains methods such as __add__, __remove__, __get__ that are used in managing the children. The component can be a leaf object or composite.
id:: 59c38393-d224-475b-a46a-0bae08f3ea5e

		 - **Composite:** it is the subclass that implements a component. It is composed of other components (children).
id:: 3c40b1ba-6ac2-4f72-9082-aa7c65be0d29

		 - **Leaf:** it is the subclass that implements a component. It does not have children.
id:: 460a0286-f47d-415b-9761-f4922942deca

	 - In plain words
id:: 5f4a60eb-293b-4523-afe1-2657ed8e5ef7
		 - Composite pattern lets clients treat the individual objects in a uniform manner.
id:: 093a2be4-be9d-4ddb-921d-c5e6e2ccb539

	 - Wikipedia says
id:: 0b27ba39-1ae0-44e2-aa41-0001d1f91e5c
		 - In software engineering, the composite pattern is a partitioning design pattern. The composite pattern describes that a group of objects is to be treated in the same way as a single instance of an object. The intent of a composite is to "compose" objects into tree structures to represent part-whole hierarchies. Implementing the composite pattern lets clients treat individual objects and compositions uniformly.
id:: 78517098-b7fc-4c1c-a451-bb855f0b63fe

	 - Programmatic Example 
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2F-BR3enf5YN.svg?alt=media&token=21a9e225-eecf-4a79-8897-e8b9a098a511)
id:: bcf21f63-e837-4a0c-8ecf-b496d847685c

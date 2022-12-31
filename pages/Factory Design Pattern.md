---
title: Factory Design Pattern
---

- The __factory pattern__ is a creational pattern that provides a template that can be used to create objects. It is used in complex situations where the type of object required varies and needs to be specified in each case. It does not use the new keyword directly to instantiate objects. This means it does not explicitly require the use of a constructor to create objects. Instead, it provides a generic interface that delegates the object creation responsibility to the corresponding subclass.
id:: e6042840-0126-4dc2-8773-9e1530199a92
	 - In plain words: the factory simply generates an instance for the client without exposing any instantiation logic to the client
id:: 9444e323-e566-4561-8760-ffd2aa874de6

	 - As the name “factory” implies, we can use this pattern when we want to create different objects that have some **similar characteristics**
id:: c4f681d7-fd33-476b-b2a6-784b01332931

	 - when to use 
id:: 6e6a598f-c9a2-49b7-85f2-932d1d84cd6b
		 - When the type of objects required cannot be anticipated beforehand
id:: c8b16d77-3d78-4777-9a13-bce1ea92c412

		 - When multiple objects that share similar characteristics need to be created
id:: 242b0f96-302e-488e-9b1a-bc6c7472e705

		 - When you want to generalize the object instantiation process since the object set-up is complex in nature
id:: f549fb0b-96f4-410f-b220-ac40f45d6b32

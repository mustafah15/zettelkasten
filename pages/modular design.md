---
title: modular design
---

- modular design 
id:: 9d4356fb-e43f-42bb-9352-75f4f48eb9de
	 - a software system is divided into modules such as classes in an object-oriented language the modules are designed to be relatively independent of each other so that a programmer can work on the module without having to understand the details of other modules. 
id:: 28688dda-e603-44bb-b13c-353883bf6321

	 - in modular design a software system is decomposed into a collection of modules that are relatively independent. Modules can take many forms, such as classes subsystems, or services, In an ideal world each module would be completely independent of the others a developer could work in any of the modules without knowing anything about the any of the other modules. in this world the complexity of the system would be the complexity of its worst module.
id:: 4f01d7c5-7b46-483d-b974-2b00603edf45

	 - unfortunately this ideal is not achievable, modules must work together by calling each other's functions or methods. as a result modules must know something about each other there will be dependencies between the modules if one module changes other modules may need to change to match 
id:: 3ef07b5f-d139-45d0-94bd-045f6eec33be

	 - The goal of modular design is to minimize  the dependencies between modules as Dependencies can take many other forms and it can be quite subtle, in order to manage dependencies, we think of each module in two parts an interface and an implementation.
id:: d42ba03a-a33f-4984-9c21-e567d888c32c

	 - [[The Module Interface]]:  consists of everything that a developer working in a different module must know in order to use the given module. Typically the interface describes what the module does but not how it does it. 
id:: d2cf4160-9579-4b5a-a23d-6fba1ec4505d

	 - [[The Module Implementation]]: consists of the code that carries out the promises made by the interface.
id:: eff7a773-7fa5-4568-bd12-7f68c0d1379f

	 - In conclusion  
id:: 0edee523-3dda-4fc0-af00-4aecba6bdfdb
		 - A developer working in a particular module must understand the interface and implementation of that module, plus the interfaces of any other modules invoked by the given module. A developer should not need to understand the implementation of modules other than the one they are working in.
id:: 35f12f82-452c-4fef-af2e-52ce972a39e3

	 - the best modules are those whose interfaces are much simpler than their implementations: such modules have two advantages. 
id:: e6250407-8d07-4f1c-9f19-b0709c9e5af7
		 - First, a simple interface minimizes the complexity that a module imposes on the rest of the system.
id:: 64f99b67-2214-4bdb-9241-3d51b5f5b716

		 - Second if a module is modified in a way that dose not change it's interface then no other module will be affected by the modification. if a module interfaces is much simpler than it's implementation there will be many aspects of the module that can be changed without affecting other modules. 
id:: 7ce7cabc-9cda-477e-9742-8bd21b7d5be0

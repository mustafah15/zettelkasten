---
title: information hiding
---

- Information Hiding
  id:: 240b7d61-2906-4885-b930-dbc7412698e8
	- the most important technique for achieving deep modules is information hiding. the basic idea is that each module should encapsulate a few pieces of knowledge, which represent design decisions. the knowledge is embedded in the implementation of the modules but does not appear in its interface so it is not visible to other modules the information hidden with the module usually consists of details about how to implement some mechanism, for example 
	  id:: fc2a3302-7f58-45ca-80e7-095b144f75c1
		- how to store information in a btree
		  id:: e52aff4e-83e0-4cf4-8485-bb9cb6986970
		- how to implement the TCP network protocol 
		  id:: 30544f1e-e30f-4a85-9bc4-2b49301b4da4
		- how to parce JSON document
		  id:: 0ddebd53-adcc-43b1-9e50-f9244ab0ea75
	- the hidden information includes data structures and algorithms related to the mechanism it can also include a lower level details such as the size of a page, and it can include higher level concepts that are more abstract such as an assumption that most files are small.
	  id:: 84fac64b-948b-4e6b-9db8-5a6d7e2a1f85
	- information hiding reduces complexity in two ways. 
	  id:: bca455a7-55d1-4f13-afe3-c4cf6e1482a1
		- first, it simplifies the interface to a module so the interface reflects a simpler more abstract view of the module's functionality and hides the details this reduces the [[cognitive load]] in developers who use the module. 
		  id:: e76ccb9f-3b89-4fd6-923f-be90d3095421
		- sconed information hiding makes it easier to evolve the system. If a piece of information is hidden there are no dependencies on that information outside the module containing the information so a design change related to that information will affect only the one module.
		  id:: 57ed5146-5dc9-4d1e-8eba-51b7e58442fa
	- when designing a new module, you should think carefully about what information can be hidden in that module. if you can hide more information, you should also be able to simplify the module's interface, and this makes the module deeper. 
	  id:: f94d0f6b-eae2-41ef-8c96-6e7e6a6c2ce7
	- hiding variables and methods in a class by declaring them private isn't the same thing as information hiding as private items can still be exposed through public methods such as getter and setter methods. when this happens the nature and usage of the variables are just exposed as if the variable were public. 
	  id:: 712171ec-dbf3-4df8-88b4-fbd1ef0d1b9c
	- the best form of information hiding is when information is totally hidden within a module so that it is irrelevant and invisible to users of the module. however partial information hiding also has a value. for example, if a particular feature or piece of information is only needed by a few of class's users and it is accessed through separate method so that it isn't visible in the most common use cases, then that information is mostly hidden such information will create fewer dependencies than information that is visible to every user of the class. 
	  id:: b0e43445-c8db-4885-a314-f757af14ecff
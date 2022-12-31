---
title: information leakage
---

- Information Leakage
id:: 58e7c674-fb1b-4b06-bddb-d08cefbd7ffd
	 - the opposite of [[information hiding]] is information leakage. 
id:: 0b4b0d6d-48ab-4e21-9e99-585ff6d8100e

	 - information leakage occurs when a design decision is reflected in multiple modules.
id:: 60236022-2c98-4978-8f51-12e8206dd43d

	 - when this happens it creates a dependency between the modules as any change to that design decision will require changes to all of the involved modules. 
id:: 610d66d8-1c3a-41eb-9865-aa422b0e9439

	 - if a piece of information is reflected in the interface for a module then by definition it has been leaked that is why simpler interfaces tend to correlate with better information hiding. ^^HOWEVER^^ information can be leaked even if it doesn't appear in a module interface. 
id:: b5169090-125f-435a-b0dc-dcee516f95c0
		 - for example suppose two classes both have knowledge of a particular file format even if neither class exposes that information in its interface, they both depend on the file format if the format changes, both classes will need to be modified.
id:: ca009ef8-c5d5-4364-b67c-fe0d6fecf223

		 - back door leakage like this is more pernicious than the leakage through an interface, because it isn't obvious. 
id:: 2710a226-d058-4556-89bb-97bce83cbfae

	 - information leakage is one of the most important red flags in software design. one of the best skills you can learn as a software designer is a high level of sensitivity to information leakage.
id:: 274339b8-7391-42fe-be87-e7fc09cc8616

	 - How to prevent information leakage?
id:: 790dca98-2c6c-436a-b942-355bce24bf36
		 - if you think you have information leakage in your design ask your self 
id:: efeed769-9d2c-4a7f-8ded-4c71cf6f93e5
			 - How Can I reorganize these classes so that this particular piece of knowledge only affects a single class?
id:: 8f982716-c0d3-4c0e-8b09-57cf5ca7057a

			 - if the affected classes are relatively small and closely tied to the leaked information, it may make sense to merge them into a single class
id:: a46c3f71-05d8-4f5c-916f-dce7bfce33f9

			 - another possible approach is to pull the information out of all of the affected classes and create a new class that encapsulates just that information. however, this approach will be effective only if you find a simple interface that abstracted away from the details if the new class exposes most of the knowledge through its interface then it won't provide much value as you simply replaced back-door leakage with leakage through an interface 
id:: b16d7754-200c-42ea-90a1-5cc7098ba216

	 - leakage types
id:: 428113ae-6941-4b86-9aef-bf61c4c91891
		 - interface leakage 
id:: c3cba9c3-cf71-4407-aaf9-c6836806c8fc
			 - a piece of information is reflected in the interface for a module then by definition it has been leaked
id:: 46d36073-60ac-49dd-9e00-22f03d950164

		 - back door leakage
id:: 426d5b3c-47cc-4192-9cd4-846154311f77
			 - for example suppose two classes both have knowledge of a particular file format even if neither class exposes that information in its interface, they both depend on the file format if the format changes, both classes will need to be modified.
id:: 89ee735b-4d5a-4b91-8a51-520d575ada5d

	 - #[[software design red flags]]
id:: 3ac0b888-0f87-4929-a921-9d1d3cb31890

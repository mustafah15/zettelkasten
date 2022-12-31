---
title: Proxy pattern
---

- What is the proxy pattern?
id:: 0ea01b59-8c23-4dbd-8abb-1b7418e3300d
	 - As the name implies, the proxy pattern is a structural pattern that creates a proxy object. It acts as a placeholder for another object, controlling the access to it.
id:: fe6c5fb7-0e2a-410c-a681-05b049d0cac7

	 - Usually, an object has an interface with several properties/methods that a client can access. However, an object might not be able to deal with the clients’ requests alone due to heavy load or constraints such as dependency on a remote source that might cause delays (e.g., network requests). In these situations, adding a proxy helps in dividing the load with the target object.
id:: f4c1c3dc-41b8-4869-8449-9844950a6ace

	 - The proxy object looks exactly like the target object. A client might not even know that they are accessing the proxy object instead of the target object. The proxy handles the requests from the clients and forwards them to the target object, preventing undue pressure on the target.
id:: 9bf2d34e-6a5e-494a-94f1-461bb645ac86

	 - In plain words
id:: 8fc6f249-a051-4adc-a80c-7f8dd41f26cd
		 - Using the proxy pattern, a class represents the functionality of another class.
id:: 7c3abe8c-49ff-42a9-87d1-b76a8343ef40

	 - Wikipedia says
id:: 7aed24df-e3f9-43b9-b550-5c006dc2bcdf
		 - A proxy, in its most general form, is a class functioning as an interface to something else. A proxy is a wrapper or agent object that is being called by the client to access the real serving object behind the scenes. Use of the proxy can simply be forwarded to the real object or can provide additional logic. In the proxy extra functionality can be provided, for example, caching when operations on the real object are resource-intensive, or checking preconditions before operations on the real object is invoked.
id:: d6f80127-4443-4867-b009-3098021c5b6d

	 - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2FinuPKtVMPB.png?alt=media&token=43d20db1-a0e1-4d3b-9ea0-7c5908a72fa0)
id:: d441749c-578b-4716-a15b-683c20894c97

	 - When to use the proxy pattern?
id:: 1894f249-3adb-47e7-8948-cc8a3e720b46
		 - The proxy pattern tries to reduce the workload on the target object. You can use it when dealing with heavy applications that perform a lot of network requests. Since delays could occur when responding to such requests, using a proxy pattern will allow the target object to not get overburdened with requests.
id:: a9f923e3-733b-4b3b-86ac-dc054b52ee33

		 - A real-life example is HTTP requests. These are expensive operations, therefore, the proxy pattern helps in reducing the number of requests forwarded to the target.
id:: fa219edd-f9bc-437c-af66-1c2121ce99bd

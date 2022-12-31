---
title: What is a messaging system?
---

- What is a messaging system?
id:: 4d35b715-f520-41ca-9422-5b8059216273
	 - A **messaging system** is responsible for transferring data among services, applications, processes, or servers. Such a system helps **decouple** different parts of a distributed system by providing an **asynchronous** way of transferring messaging between the sender and the receiver. Hence, all senders (or producers) and receivers (or consumers) focus on the data/message without worrying about the mechanism used to share the data.
id:: 3a83a69a-4cff-4b18-b420-27938f0798ba

	 - There are two common ways to handle messages:
id:: b2ff1818-d706-482b-aa6f-4d40b4d1f7dd

	 - [[Queuing]]
id:: 8690de9f-ecff-47c2-b5e9-307629c31cac
		 - ((4e2abf76-9fa4-4d60-bfb9-650e0619c1fe))
id:: 391979b2-a4f6-4594-8e44-15c803a76a3a
			 - ((5b9a96a2-e7ad-4fef-a637-e5b33ac5cfd2))
id:: d2801ad1-003a-47a3-bf63-bac76d57d8ab

			 - ((9a3cd9b0-548f-4b78-80ad-2fcd20ae47db))
id:: e6302e44-29ae-4cf3-aa4b-9466236f6dc4

			 - ((d598bbf5-1049-497a-a7a9-bf5a02b4f85e))
id:: 37af5c11-7ad7-4940-9927-b6be5bcedff7

	 - [[Publish-Subscribe]]
id:: 067301c3-e9a7-4855-8937-623f37f7523a
		 - ((1fef11e1-e4d1-45d4-8c65-ea8b97419ab5))
id:: 6a14efb4-f6bb-4eaf-8e0d-c9e70f46ffe2
			 - ((6354b380-6935-447a-a3d7-b39c5db9cc68))
id:: 095282b5-a761-4796-a079-079a404356db

			 - ((8cf9ee9a-8f44-4af5-8ed2-9c9e38787159))
id:: 5e1a7abf-97eb-4be2-bc4c-79241591c09b

			 - ((a1ae5030-61f8-4065-8297-785598876725))
id:: c945c630-3af9-4909-8115-6dc25938db78

			 - ((d8cd65f0-6e0b-41b5-988d-f9aead8b41ca))
id:: c131bf5e-828d-4929-9903-3ad01250eae1

			 - ((875fc146-8841-41b6-a883-57b6ec015320))
id:: 472f7b12-d5cb-4114-966f-ea8913c1dbd8

	 - a message system is deployed in an application stack for the following reasons:
id:: 15d8b847-3480-489b-a9de-bee0ff3b541f
		 - **Messaging buffering**. To provide a buffering mechanism in front of processing (i.e., to deal with temporary incoming message spikes that are greater than what the processing app can deal with). This enables the system to safely deal with spikes in workloads by temporarily storing data until it is ready for processing.
id:: c2ae969c-fd9f-4d74-8912-fe7f90c45c86

		 - **Guarantee of message delivery**. Allows producers to publishing messages with assurance that the message will eventually be delivered if the consuming application is unable to receive the message when it is published.
id:: 09d85d1a-262a-4685-9290-07962afcc29a

		 - **Providing abstraction**. A messaging system provides an architectural separation between the consumers of messages and the applications producing the messages.
id:: 45b71467-c14d-498a-b206-e8befac5896a

		 - **Enabling scale**. Provides a flexible and highly configurable architecture that enables many producers to deliver messages to multiple consumers.
id:: 16473bf0-4e99-4686-8fe5-9bb6bbb890c5

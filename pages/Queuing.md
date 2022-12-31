---
title: Queuing
---

- Queuing
id:: 4e2abf76-9fa4-4d60-bfb9-650e0619c1fe
	 - In the queuing model, messages are stored sequentially in a queue. Producers push messages to the rear of the queue, and consumers extract the messages from the front of the queue.
id:: 5b9a96a2-e7ad-4fef-a637-e5b33ac5cfd2

	 - A particular message can be consumed by a maximum of one consumer only. Once a consumer grabs a message, it is removed from the queue such that the next consumer will get the next message. This is a great model for distributing message-processing among multiple consumers. But this also limits the system as multiple consumers cannot read the same message from the queue.
id:: 9a3cd9b0-548f-4b78-80ad-2fcd20ae47db

	 - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2FRwL21E12zz.png?alt=media&token=a9a68117-af09-4f5c-9640-5a6e6d1bc7bf)
id:: d598bbf5-1049-497a-a7a9-bf5a02b4f85e

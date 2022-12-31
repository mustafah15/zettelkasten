---
title: Communication and Coordination
---

- interprocess communication between system nodes over the network is at the heart of distributed systems.

- In this part, we will focus on the communication styles so we start getting the grasp of what communication style/technique suits our system better.

- before we start our discussion we first we will

- **APIs** a service exposes operations to its consumers via a set of interfaces implemented by its business logic. as remote clients can't access these directly. Adapters that make up the service application programming interface (API) translate messages received from IPC to interface requests.

- The communication style between a client and a service can be direct or indirect, depending on whether the client communicates directly with the service or indirectly with it through a broker.

- **Direct communication** requires that both processes are up and running for the communication to succeed. However, sometimes this guarantee is either not needed or very hard to achieve in which case indirect communication can be used.

- In this part, we will focus our attention on a direct communication style which is called request-response, in which a client sends a request to the service and the service replies back with a response message. this is similar to a function call, but across process boundaries and over the network. The format impacts a message’s serialization and deserialization speed, whether it’s human-readable, and how hard it is to evolve it over time. A textual format like JSON is self-describing and human-readable, at the expense of increased verbosity and parsing overhead. On the other hand, a binary format like Protocol Buffers is leaner and more performant than a textual one at the expense of human readability.

- when a client sends a request to a service, it can block and wait for the response to arrive, making communication synchronous. 

- **Synchronous communication** can be inefficient, as it blocks threads that could be used to do something else. Some languages, like JavaScript and C#, can completely hide callbacks through language primitives such as async/await. These primitives make writing asynchronous code as straightforward as writing synchronous one. the request and the response message should contain data that is serialised in a language-agnostic format.

- the most commonly used IPC direct communication technologies are REST, gRPC and GraphQL.

- **async communication **

- coordination 
	 - some models for communication links:
		 - The fair-loss link model assumes that messages may be lost and duplicated. But if the sender keeps retransmitting a message, eventually it will be delivered to the destination.

		 - The reliable link model assumes that a message is delivered exactly once, without loss or duplication. A reliable link can be implemented on top of a fair-loss one by de-duplicating messages at the receiving side.

		 - The authenticated reliable link model makes the same assumptions as the reliable link but additionally assumes that the receiver can authenticate the sender.

	 - We can also model the different types of process failures we expect to happen:
		 - The arbitrary-fault model assumes that a process can deviate from its algorithm in arbitrary ways, leading to crashes or unexpected behaviour due to bugs or malicious activity. This model is also referred to as the “Byzantine” model for historical reasons. Interestingly, it can be theoretically proven that a system using this model can tolerate up to one-third of faulty processes and still operate correctly.

		 - The crash-recovery model assumes that a process doesn’t deviate from its algorithm, but can crash and restart at any time, losing its in-memory state.

		 - The crash-stop model assumes that a process doesn’t deviate from its algorithm, but if it crashes it never comes back online.

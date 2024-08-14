---
tags:
  - distributed-systems
type:
  - fleeting
aliases:
  - async communication
  - asynchronous communication
related:
---

### What is asynchronous messaging?

In asynchronous messaging, messages are not directly sent from one service to another . This is done via another component in the middle which receives messages from the sender service, enqueues them, and finally dispatches the messages to the receiver service. The component in the middle is called the **message broker** or **message queue**. The sender is generally denoted as the **producer**, whereas the receiver is the **consumer**.
in this scenario, a service sends messages to the queue, which works as a buffer. The other service listens to the queue and receives the messages. In formal terms, Service 1 is the producer that produces the messages, and Service 2 is the consumer that consumes them.


We should now see why this is called asynchronous messaging. In this mechanism, the services do not send messages directly anymore. There is the middleman, which works as a buffer. So there is no further synchronous communication between the services as the client service receives a response at some point and asynchronously handles it. Any of the services can independently start, pause, or resume. No direct connection is required between the two services.

### Advantages of asynchronous messaging

This data circulation method has a number of advantages over other mechanisms. Let’s discuss them briefly:
- **Messaging buffering**. To provide a buffering mechanism in front of processing (i.e., to deal with temporary incoming message spikes that are greater than what the processing app can deal with). This enables the system to safely deal with spikes in workloads by temporarily storing data until it is ready for processing.
- **Guarantee of message delivery**. Allows producers to publishing messages with assurance that the message will eventually be delivered if the consuming application is unable to receive the message when it is published.
- **Providing abstraction**. A messaging system provides an architectural separation between the consumers of messages and the applications producing the messages.
- **Enabling scale**. Provides a flexible and highly configurable architecture that enables many producers to deliver messages to multiple consumers.


It is more natural to implement asynchronous communication with an asynchronous communication protocol. An asynchronous communication protocol **sends messages and does not expect responses**. In messaging systems like [[kafka]] asynchronous communication, the coupling of systems can be driven to different lengths.
for example:
- a system for **order processing** could inform the **invoice** system asynchronously that an invoice has to be written.
- The ordering system thus determines exactly what the invoicing system has to do: generate an invoice.
- It also sends a message to the bounded context **shipping** to trigger the delivery.

The system can also be set up differently. The focus will then be on an event like, “There is a new order.” Every microservice can react appropriately to this:

- The **invoicing** system can write an invoice.
- The **shipping** system can prepare the goods for delivery.

Each microservice decides for itself how it reacts to the events, see the drawing below.

![[event-async-communication.png]]


This leads to **better decoupling**. If a microservice has to react differently to a new order, the microservice can implement this change on its own.
It is also possible to **add a new microservice** that generates statistics when a new order is placed.


- types of async communication 
	- [[event-based communication]]
	- [[message-based communication]]
	- 
- event-based vs. message-based communication
	-  A message is an item of data that is sent to a specific destination. An event is a signal emitted by a component upon reaching a given state. In a message-driven system, addressable recipients await the arrival of messages and react to them, otherwise lying dormant. In an event-driven system, notification listeners are attached to the sources of events such that they are invoked when the event is emitted. This means that an event-driven system focuses on addressable event sources while a message-driven system concentrates on addressable recipients. A message can contain an encoded event as its payload.
	- example:
		-  **Message-driven**: When an order is placed, the Order service sends an authorization request to your Payment service. Your service processes the request and returns success/failure to the Order service. The initial request and the result could be sent synchronously or asynchronously.
		- **Event-driven**: When an order is placed, the Order service publishes a NewOrder event. Your Payment service subscribes to that type of event so it is triggered. Your service processes the request and either publishes an AuthorizationAccepted or an AuthorizationDeclined event. The Order service subscribes to those event types. All events are asynchronous.


### [[what is a messaging system?]]

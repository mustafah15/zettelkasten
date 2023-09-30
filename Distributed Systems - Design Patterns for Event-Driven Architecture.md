---
tags:
  - distributed-systems
  - system-design
type:
  - fleeting
related: "[[distributed systems]]"
---

# 1. Event Sourcing

Event Sourcing is a powerful design pattern that offers a different approach to system state storage. Traditional methods usually involve saving the current state of the data. Event Sourcing, on the other hand, involves storing all changes (events) that cause the state to change, instead of the state itself.

In an event-sourced system, events are immutable facts of things that happened. These events are stored in the order they were created (often in an append-only event store) and can be queried and used to derive the current state of the system at any point in time.

This design pattern comes with several **advantages**:

1. **Historical State**: Since all changes are stored, it’s possible to recreate the state of the system at any point in time. This is extremely valuable for debugging and audit purposes, or for providing historical data analysis.

2. **Auditability**: Event Sourcing provides a reliable audit log out of the box. The event store serves as a log of all changes, making it easy to see who did what and when.

3. **Event Replay**: Since all events are stored, they can be replayed to recreate the state. This is useful for testing, debugging, or even migrating to a different state structure.

4. **Temporal Query**: You can ask questions about the state of the system at any point in time. For example, “What was the state of user X’s shopping cart on date Y?”

However, it’s important to note that Event Sourcing also has its complexities and isn’t a one-size-fits-all solution:

1. **Event Schema Changes**: Over time, the structure of your events might change. Handling these changes can be challenging since events are immutable.

2. **Performance Considerations**: Recreating state by replaying all events could be slow if there are many events. Solutions to this include using snapshots of the state at different points in time.

3. **Complexity**: Event Sourcing introduces a level of complexity that may be unnecessary for simple applications. It’s typically used in systems where the benefits of having a complete history and the ability to easily reconstruct past states outweigh the added complexity.

In summary, Event Sourcing is a powerful design pattern that can provide significant benefits when applied correctly. However, it requires careful thought and design to ensure that it fits the system’s needs and to handle the inherent complexities effectively.

# 2. CQRS (Command Query Responsibility Segregation)

Command Query Responsibility Segregation (CQRS) is a design pattern that separates read operations (queries) from write operations (commands) in a system. This distinction allows each operation to be optimized separately and handled by different models or even different services, thus enhancing the performance, scalability, and security of the system.

In a traditional CRUD (Create, Read, Update, Delete) model, the same data model is used for both read and write operations. However, in many systems, especially complex ones, the requirements and performance characteristics for reads and writes can be very different.

CQRS addresses this by creating two separate models:

1. **Command Model**: This model handles all write operations. It’s responsible for maintaining consistency of the system’s state and includes business logic to validate and process commands.
2. **Query Model:** This model handles all read operations. It’s optimized for querying, often with a denormalized data model that is structured to support the system’s specific read patterns.

The **benefits** of **CQRS** include:

1. **Performance Optimization**: By separating reads and writes, each can be optimized independently. This can lead to significant performance improvements for both operations.
2. **Scalability**: Each model can scale independently based on its workload. For example, if a system has a high read load but a low write load, more resources can be allocated to the query model.
3. **Flexibility**: Different models can be designed to best meet the needs of different operations. For example, the command model might be highly normalized to prevent data redundancy, while the query model might be denormalized to support efficient querying.
4. **Security**: By segregating commands and queries, it’s easier to apply different security rules for reading and writing data.

However, as with any pattern, **CQRS** also has its complexities and isn’t always the right choice:

1. **Increased Complexity**: Introducing CQRS adds complexity to the system. It requires maintaining two separate models, which can lead to more code and potential for bugs.
2. **Data Synchronization**: Ensuring that the command and query models are synchronized can be challenging, especially in systems with high levels of concurrency.
3. **Eventual Consistency**: In many CQRS implementations, the command model and query model are updated asynchronously, leading to a state of [eventual consistency](https://blog.bitsrc.io/eventual-consistency-in-microservices-a8106d8dd0ab). This means there might be a delay before a change made by a command is visible to the query model.

In summary, **CQRS** can offer significant benefits when used in the right context, particularly for complex, high-load systems where the needs of reads and writes are very different. However, it’s important to carefully consider the additional complexity it introduces and ensure it’s the right fit for the system’s needs.

# 3. Event Carried State Transfer

Event Carried State Transfer is a design pattern in which a service publishes events containing enough information about a change so that other services that receive the event can update their own state, without needing to request additional data.

In distributed systems, services often need to share data. One common way to do this is to make a remote call to the service that owns the data. This, however, can lead to tight coupling between services and can impact performance, as the services must wait for the remote call to complete.

The **Event** **Carried** **State** **Transfer** pattern offers an alternative approach. Instead of making a call to fetch data when it’s needed, services listen for events that indicate the data has changed. These events contain all the relevant data related to the change. When a service receives an event, it uses the data in the event to update its own local copy of the data.

This approach has several **benefits**:

1. **Decoupling**: Services do not need to make synchronous calls to each other, which reduces coupling and increases the autonomy of each service.
2. **Performance**: Because services are not making remote calls to fetch data, the system can often perform better and be more responsive.
3. **Resilience**: If a service goes down, it won’t affect other services as they have their own local copy of the data they need.

However, there are also some considerations and potential drawbacks:

1. **Data Duplication:** This pattern involves replicating data across services, which can lead to increased storage requirements and the potential for inconsistency if not managed carefully.
2. **Event Content**: Deciding what data to include in events can be challenging. Include too little, and services may still need to make calls to fetch data. Include too much, and you could be sharing data unnecessarily, potentially violating principles of data privacy and security.
3. **Data Synchronization**: Managing updates to ensure all services have a consistent view of the data can be complex, particularly in systems with high levels of concurrency.

In summary, **Event Carried State Transfer** can be a powerful pattern for managing data sharing in distributed, event-driven systems. As with all patterns, it’s important to consider the specific needs and constraints of your system to determine if it’s the right approach.

# 4. Saga Pattern

The Saga Pattern is a design pattern that provides an effective way to manage transactions that span multiple services in a distributed system.

In a monolithic application, you might use a distributed transaction that spans multiple tables, rows, or even databases to maintain data consistency. However, in a distributed system, where components are spread across different networked computers, managing transactions that span multiple services can be challenging.

The Saga pattern offers a solution to this problem. It breaks a transaction into a series of local transactions, each of which updates data within a single service. After executing a local transaction, a service publishes an event to trigger the next local transaction in the saga.

If all the local transactions are completed successfully, then the overall saga is successful. However, if a local transaction fails for some reason, the saga executes a series of compensating transactions to undo the impact of the preceding local transactions.

The benefits of the **Saga Pattern** include:

1. **Maintaining Data Consistency**: The Saga pattern provides a mechanism for maintaining data consistency across multiple services in an event-driven, distributed system.
2. **Failure Management**: By using compensating transactions, the Saga pattern can effectively handle failures and exceptions, helping to ensure the overall consistency of the system.
3. **Loose Coupling**: Each service in a saga can operate and evolve independently, increasing the flexibility and scalability of the system.

However, there are also some considerations and challenges:

1. **Complexity:** Managing sagas and compensating transactions can add complexity to the system, both in terms of development and operation.
2. **Eventual Consistency**: The Saga pattern leads to a system that is eventually consistent. Depending on the nature of the business operations, eventual consistency might be a difficult concept to handle.
3. **Compensating Transaction Design**: Designing compensating transactions can be tricky. They must effectively undo the changes of the previous transactions while dealing with the possibility that some of those changes could have already been processed by other services.

In conclusion, the **Saga** **Pattern** is a key strategy for managing transactions and ensuring data consistency in a distributed event-driven system. It’s important to carefully design the local and compensating transactions to ensure they correctly maintain the consistency of the system.

# 5. Back Pressure Pattern

Back Pressure is a design pattern used to handle situations where a system component is overloaded with too many requests or data. This pattern is particularly useful in event-driven architectures where a service, or a component, may receive events at a rate faster than it can process them.

The basic idea of the Back Pressure pattern is to provide a feedback mechanism that allows a service to signal upstream that it’s overwhelmed with the current load and cannot accept any more requests or data at the moment. This can be done in several ways, such as:

1. **Buffering**: The overwhelmed component can buffer incoming requests until it has the capacity to handle them. However, this is effective only up to a certain point. If the rate of incoming requests continuously exceeds the processing rate, the buffer will eventually fill up and can cause the system to crash.
2. **Load Shedding**: The component can start dropping incoming requests when it’s overwhelmed. While this approach may result in lost data or unserved requests, it can prevent system failure in high-load situations.
3. **Throttling**: The component can slow down the rate at which it accepts new requests. This can be done by delaying the acceptance of new requests or by accepting only a certain number of requests per unit of time.
4. **Resizing**: If the system is designed to be elastic, it can respond to high load by automatically adding more resources or instances of the overwhelmed component.

The **benefits** of the **Back** **Pressure** pattern include:

1. **Resilience**: By actively managing overload situations, the Back Pressure pattern can prevent system failure and improve overall resilience.
2. **Flow Control**: Back Pressure can help manage the flow of data or requests through the system, helping to ensure that all components operate within their capacity.

However, there are also some **challenges** and **considerations**:

1. **Lost Data or Requests**: Depending on how Back Pressure is implemented, it might result in lost data or unserved requests.
2. **Complexity**: Implementing Back Pressure can add complexity to the system. It requires careful design to ensure that signals are properly propagated and handled.
3. **User Experience**: Back Pressure can impact the user experience, as it can result in slower response times or dropped requests. It’s important to handle these situations in a way that minimizes the impact on users.

In summary, the **Back** **Pressure** pattern is an important strategy for managing overload situations in event-driven systems. While it can add complexity and potentially impact the user experience, it’s crucial for maintaining the resilience and stability of the system.
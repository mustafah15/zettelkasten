---
tags:
  - software-design
type: permanent
related: "[[distributed systems - design patterns for event-driven architecture]]"
---
## Event-Driven Architecture (EDA)

**EDA** is an architectural style where components communicate primarily through events. Systems react to events asynchronously rather than through direct calls.

Key characteristics:
- Loose coupling between components
- Asynchronous communication (usually via message brokers)
- Components publish events without knowing who consumes them
- Enables scalability and independent deployment

Example: An order service publishes events to a message bus; inventory, shipping, and notification services each subscribe and react independently.


- **EDA** often uses [[ddd domain event]] as the messages passed between *services
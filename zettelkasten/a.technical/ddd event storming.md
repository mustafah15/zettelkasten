---
tags:
  - ddd
  - software-design
type: permanent
related: "[[DDD - tactical patterns]]"
---
## What is Event Storming?
  
**Event Storming** is a **collaborative workshop** technique used to **explore complex domains** by mapping out **domain events** in a visual, timeline-like format. It helps domain experts, developers, and stakeholders **build a shared understanding** of the system.
- Invented by **Alberto Brandolini**
- Focuses on [[DDD Domain Event]]
#### **🧩 Core Concepts (Post-it Colors):**

| **Type**  | **Meaning**                             | **Example**                    |
| --------- | --------------------------------------- | ------------------------------ |
| 🟠 Orange | **Domain Event** (past tense)           | OrderPlaced, PaymentReceived   |
| 🟢 Green  | **Command** (intention to do something) | PlaceOrder, CancelBooking      |
| 🔵 Blue   | **Aggregate/Entity**                    | Order, User, Product           |
| 🟡 Yellow | **Policy/Rule**                         | If payment fails, cancel order |
| 🟣 Purple | **External System/User**                | Customer, CRM System           |
| 🟥 Red    | **Problem/Hotspot**                     | “Unclear business rule here”   |
#### **✅ How to Conduct a Successful Event Storming Session**

  
**1.** **Set the Stage**
- Invite a **cross-functional group**: domain experts, developers, product owners.
- Book a large physical or virtual whiteboard space (e.g., Miro, MURAL).
- Use **sticky notes** (physical or digital) and color code them.

**2.** **Start with Domain Events (🟠)**
- Ask: “What are the key things that **happen** in the system or sub-system?”
- Place events in **chronological order**.
- Example: UserRegistered → OrderPlaced → PaymentReceived.

**3.**  **Add Commands (🟢)**
- For each event, ask: “What action caused this to happen?”
- Example: PlaceOrder leads to OrderPlaced.

**4. Identify Aggregates (🔵)**
- Ask: “What entity holds the logic or ensures consistency?”
- Example: Order aggregate handles the PlaceOrder command.

 **5.** **Insert Policies (🟡)**
- Ask: “What should automatically happen after this event?”
- Example: After OrderPlaced, send confirmation email.

 **6.** **Add External Actors (🟣)**
- Who triggers commands or receives events?
- Example: Customer initiates PlaceOrder.

 **7.**  **Mark Hotspots (🟥)**
- Capture unclear, risky, or contentious areas.
- Useful for follow-up discussions or deeper dives.
  
**8.** **Group and Refactor**
- Spot **bounded contexts** naturally forming.
- Cluster events/commands by business subdomains.
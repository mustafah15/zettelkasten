---
tags:
  - ddd
  - software-design
type:
  - literature
related: "[[domain driven design]]"
---


- Commands
    - Commands are a type of activity that occurs in the domain.
    - Represents a request to preform an action.
    - the action has not yet happened and it can be rejected.
    - Usually delivers to aa specific destination causes a change to the state of the domain.
    - Eg. Add an item to an order, pay a bill.

- Events
    - Events are another type of activities in the domain.
    - They represent an action that happened in the past.
    - because of the action already completed, they can not be rejected.
    - often broadcast to many destinations.
    - record a change to the state of the domain, often the result of aa command.
    - Eg. item was added to an order, a bill was paid, aa meal was prepared.
- Quereis
    - they represent a request for information about the domain.
    - because they are a query, a response is always expected.
    - usually delivered to a specific destination
    - queries should not alter the state of the domain
    - Eg. get all the details of an order, check if a bill haas been paid.


![[relation-betweencommand-query-event.png]]

relation between command event and query.

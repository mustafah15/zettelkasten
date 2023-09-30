---
tags:
  - system-design
  - ddd
type:
  - fleeting
aliases:
  - bounded context
related: "[[domain driven design]]"
---
In domain-driven design (DDD), a bounded context is a linguistic and organizational boundary defining a specific business domain area. A bounded context defines a specific set of concepts, terminology, and business rules that apply within that context while excluding concepts and rules that apply in other contexts.

In the context of microservices, bounded contexts are particularly relevant because they help ensure that each microservice is focused on a specific business capability or domain and that the models used in each microservice are tailored to that specific domain. When designing microservices, defining the primary domains and subdomains, boundaries of business rules, processes, and interactions around them are known as bounded context.

In the example of a product delivery management that sells products, each subdomain could be considered a bounded context. The product catalog, for example, would have its own bounded context that defines the concepts and rules related to managing the product catalog. Order management would have its own bounded context that defines the concepts and rules related to the ordering process, and so on. Each subdomain’s domain model would be a bounded context, and the overall system domain model would comprise all these bounded contexts.

Bounded Context encourages an object-model-first strategy for developing services bounded to a data model. It is merely the dividing line within a domain where a specific domain model is applicable. Dealing with large models and teams requires categorizing them into various Bounded Contexts and being specific about how those contexts interact. As a result, it is accountable for the integrity and mutability of the data model.

Also, by defining clear boundaries between bounded contexts, teams can work independently on their respective microservices without interfering with each other. This promotes better isolation and encapsulation, making it easier to maintain and modify individual microservices without impacting the rest of the system.

Bounded contexts establish clear boundaries around a cohesive area of the business domain, and smaller, focused teams can own these discrete parts of business responsibilities instead of whole projects.
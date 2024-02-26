---
tags:
  - book-notes
  - ddd
related: "[[lddd - integrating bounded context with cooperation pattern]]"
type:
  - literature
aliases:
  - lddd - integrating bounded contexts with shared kernel
---
### Shared Kernel 
Despite [[DDD - bounded context|bounded context]] being model boundaries there still can be cases when the same model of a subdomain or a part of it will be implemented in multiple bounded contexts, it's crucial to stress that the shared model is designed according to the needs of all the bounded contexts more over the shared model has to be consistent across all of the bounded contexts that are using it.
- an example, consider an enterprise system that uses a model for managing user permissions each user can have their permissions granted directly or inherited from one of the organization models, more over each bounded context can modify the authorization model, and the changes each bounded context applies have to affect all the other bounded context using the model
![[Screenshot 2024-02-20 at 21.02.33.png]]

#### Shared Scope
The overlapping model couples the lifecycle of the participating bounded context. A change made to the shared model has an immediate effect on all the bounded contexts Hence, to minimize the cascading effects of changes, the overlapping model should be limited, exposing only that part of the model that has to be implemented by both bounded contexts, Ideally, the shared kernel will consist only of integration contracts and the data structures that are intended to be passed across the bounded contexts boundaries. 

#### Implementation 
The Shared Kernel is implemented so that any modification to its source code is immediately reflected in all the bounded contexts using it.
If the organization uses the mono-repo approach these can be the same source files referenced by multiple bounded contexts if using a shared repository is not possible the shared kernel can be extracted into a dedicated project and referenced in the bounded contexts as a linked library, Either way, each change to the shared kernel must trigger integration tests for all the affected bounded contexts.

The continued integration of changes is required because the shared kernel belongs to multiple bounded contexts. Not propagating shared kernel changes to all related bounded contexts leads to inconsistencies in a model; bounded contexts may rely on stale implementation of the shared kernel, leading to data corruption and/or run time issues.

#### when to use shared kernel

> [!NOTE] Important to know 

The applicability for the shared kernel pattern is the cost of duplication versus the cost of coordination, since the pattern introduces a strong dependency between the participating bounded contexts it should be applied only when the cost of duplication is higher than the cost of coordination -in other words only when integrating changes applied to the shared model by both bounded contexts will require more effort than coordinating the changes in the shared codebase.

the difference between the integration and duplication costs depends on the volatility of the model, the more frequently it changes the higher the integration costs will be therefore the shared kernel will naturally be applied for the subdomains that change the most (the core subdomains)


> [!tldr] Important to Note that 
> 

The shared kernel pattern contradicts the principles of [[DDD - bounded context]] introduced before as introducing a shared kernel contradicts the principle that a single team should own a bounded context, The overlapping model - the shared kernel - is owned and developed by multiple teams.

The reason why the use of a shared kernel has to be justified is that it is a pragmatic exception that should be considered carefully.

#### Shared Kernel Use cases
- A common use case for implementing a shared kernel is when communication or collaboration issues prevent the [[lddd - integrating bounded contexts with partnership|bounded context partnership]]
- Another common use case for applying the shared kernel is a temporary one is the gradual modernization of a legacy system in such systems the shared code base can be a pragmatic intermediate solution for gradually decomposing a system into bounded contexts. 

A shared kernel can be a good fit for integrating bounded contexts owned and implemented by the same team in such a case as an ad hoc integration of the bounded contexts a shared kernel can be used for explicitly defining the bounded contexts integration.

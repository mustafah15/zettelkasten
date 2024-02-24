---
tags:
  - book-notes
related: "[[lddd - integrating bounded contexts]]"
type:
  - literature
---


## Cooperation

Cooperation patterns related to bounded contexts are implemented by teams with well-established communication. 
In the simplest case, these are bounded contexts implemented by a single team. this also applies to teams with dependent goals, where one team's success depends on the success of the other and vice versa. again the main criterion here is the quality of the team communication and collaboration.
There are two DDD patterns suitable for cooperating teams: the partnership and shared kernel patterns.

### Partnership
In the partnership model, the integration between bounded contexts is coordinated in an ad hoc manner one team can notify another team about a change in the API and the second team will cooperate and adopt 

![[Screenshot 2024-02-20 at 20.43.59.png]]
The Coordination of integration here is two-way no one team dictates the language that is used for defining the contracts. The teams can work out the differences and choose the most appropriate solutions also both sides cooperate in solving any integration issues that might come up neither team is interested in blocking the other one. 
high levels of commitment and frequent synchronization between teams are **required** for successful integration in this manner 
This Pattern might not be a good fit for geographically distributed teams since it may present synchronization and communication challenges. also might be hard for two different teams in different companies to work on such a model.

### Shared Kernel 

Despite bounded contexts being model boundaries there still can be cases when the same model of a subdomain or a part of it will be implemented in multiple bounded contexts, it's crucial to stress that the shared model is designed according to the needs of all the bounded contexts more over the shared model has to be consistent across all of the bounded contexts that are using it.

- an example, consider an enterprise system that uses a model for managing user permissions each user can have their permissions granted directly or inherited from one of the organization model, more over each bounded context can modify the authorization model, and the changes each bounded context applies have to affect all the other bounded context using the model
![[Screenshot 2024-02-20 at 21.02.33.png]]

#### Shared Scope
The overlapping model couples the lifecycle of the participating bounded context. A change made to the shared model has an immediate effect on all the bounded contexts Hence, to minimize the cascading effects of changes, the overlapping model should be limited, exposing only that part of the model that has to be implemented by both bounded contexts, Ideally, the shared kernel will consist only of integration contracts and the data structures that are intended to be passed across the bounded contexts boundaries. 

#### Implementation 
The Shared Kernel is implemented so that any modification to its source code is immediately reflected in all the bounded contexts using it.
If the organization uses the mono-repo approach these can be the same source files referenced by multiple bounded contexts if using a shared repository is not possible the shared kernel can be extracted into a dedicated project and referenced in the bounded contexts as a linked library, Either way each change to the shared kernel must trigger integration tests for all the affected bounded contexts.

The continued integration of changes is required because the shared kernel belongs to multiple bounded contexts. Not propagating shared kernel changes to all related bounded contexts leads to inconsistencies in a model; bounded contexts may rely on stale implementation of the shared kernel, leading to data corruption and/or run time issues.

#### when to use shared kernel



> [!NOTE] Important to know 

the applicability for the shared kernel pattern is the cost of duplication versus the cost of coordination, since the pattern introduces a strong dependency between the participating bounded contexts it should be applied only when the cost of duplication is higher than the cost of coordination -in other words only when integrating changes applied to the shared model by both bounded contexts will require more effort than coordinating the changes in the shared codebase.

the difference between the integration and duplication costs depends on the volatility of the model, the more frequently it changes the higher the integration costs will be therefore the shared kernel will naturally be applied for the subdomains that change the most (the core subdomains)


> [!tldr] Important to Note that 
> 

The shared kernel pattern contradicts the principles of [[DDD - bounded context]] introduced before as introducing a shared kernel contradicts the principle of a single team should own a bounded context, The overlapping model - the shared kernel - is owned and developed by multiple teams.

The reason why the use of a shared kernel has to be justified it is a pragmatic exception that should be considered carefully.

#### Shared Kernel Use cases

- A common use case for implementing a shared kernel is when communication or collaboration issues prevent the partnership pattern
- Another common use case for applying the shared kernel is a temporary one is the gradual modernization of a legacy system in such systems the shared code base can be a pragmatic intermediate solution for gradually decomposing a system into bounded contexts. 

A shared kernel can be a good fit for integrating bounded contexts owned and implemented by the same team in such a case as an ad hoc integration of the bounded contexts a shared kernel can be used for explicitly defining the bounded contexts integration.

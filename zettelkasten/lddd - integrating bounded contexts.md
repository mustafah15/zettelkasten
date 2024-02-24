---
tags:
  - book-notes
  - ddd
related: "[[learning domain driven design|lddd]]"
type:
  - literature
---
not only does the bounded context protect the consistency of a ubiquitous language but it also enables modeling, you can't build a model without specifying its purpose and its boundary the boundary divides the responsibility of languages as A language in one bounded context can model the business domain to solve a particular problem another bounded context can represent the same business entities but model them to solve a different problem. 

Bounded contexts themselves are not independent just as a system cannot be built out of independent components the components have to interact with one another to achieve  the system's overarching goals, and so too do the implementations in bounded contexts although they can evolve independently they have to integrate as a result there will always be touch points between bounded context these are called ==Contracts==

Why contracts are needed in the context of DDD?
The need for contracts results from differences in bounded contexts models and languages Since each contract affects more than one party they need to be defined and coordinated also by definitions two bounded contexts are using different ubiquitous languages which language will be used for integration purposes? these integration concerns should be addressed by the solution's design. 

DDD Patterns for defining relationships and integration between bounded contexts

Cooperation, Customer-Supplier, and Separate Ways.


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

## Customer - Supplier 

The second group of collaboration patterns is the customer-supplier where one of the bounded contexts the supplier provides a service for its customers the service provider is the upstream and the customer is the downstream.

![[Screenshot 2024-02-21 at 08.34.43.png]]
unlike the cooperation case both upstream and downstream can succeed independently. In most cases we have an imbalance of power: either the upstream or the downstream team can dictate the integration contract.

### Conformist
As the relation between [[customer-supplier]] pattern goes, if the case is the balance of power favors the upstream team, which has no real motivation to support its client's needs instead it just provides the integration contract, defined according to its own model such power imbalances can be caused by integration with service providers that are external to the organization or simple by organizational politics. 

If the downstream team can accept the upstream model, the bounded contexts relationship is called conformist, as the downstream confirms to the upstream bounded contexts model

![[Screenshot 2024-02-24 at 07.12.32.png]]

the downstream team's decision to give up some of its autonomy can be justified in multiple ways. for example, the contract exposed by the upstream team may be an industry-standard model, or it may be just good enough for the downstream team's need

### Anticorruption Layer
As we are still in the customer-supplier pattern and if the balance of power is still toward the upstream service as in the [[conformist pattern]] case, however in this case the downstream bounded context is not willing to conform instead it can translate the upstream bounded context's model into a model tailored to its own needs via an anticorruption layer as shown below 

![[Screenshot 2024-02-24 at 07.34.56.png]]

The anti-corruption layer pattern addresses scenarios in which it is not desirable or worth the effort to conform to the supplier's model such as the following:
- when the downstream bounded context contains a core subdomain
	- a core subdomain model requires extra attention and adhering to the supplier's model might impede the modeling of the problem domain.
- when the upstream model is insufficient or inconvenient for the consumer's need
	- if a bounded context conforms to a mess it risks becoming a mess itself
- when the supplier's contract changes often
	- the consumer wants to protect its model from the frequent changes
from a modeling perspective, the translation of the supplier's model isolates the downstream consumer from foreign concepts that are not relevant to its bounded context hence it simplifies the consumer's ubiquitous language and model.

### Open Host Service 
This pattern addresses the case in which the power is skewed toward the consumers the supplier is interested in protecting its consumers and providing the best service possible. 

to protect the consumers from changes in its implementation model the upstream supplier decouples the implementation model from the public interface, this decoupling allows the supplier to evolve its implementation and public models at different rates. 
![[Screenshot 2024-02-24 at 07.56.18.png]]

the supplier public interface is not intended to conform to its ubiquitous language instead it is intended to expose a protocol convenient for the consumers expressed in an integration-oriented language as such the public protocol is called the published language
in a sense, the oper-host service pattern is a reversal of the [[anti-corruption layer pattern]] instead of the consumer the supplier implements the translation of its internal model

Decoupling the bounded context's implementation and integration models gives the upstream bounded context the freedom to evolve its implementation without affecting the downstream contexts this is only possible if the modified implementation model can be translated into the published language the consumer already using. 

The integration model's decoupling allows the upstream bounded context to simultaneously expose multiple versions of the published language allowing the. consumer to migrate to the new version gradually 
![[Screenshot 2024-02-24 at 08.05.09.png]]


## Separate Ways
This pattern can arise for different reasons in cases where the teams are unwilling to unable to collaborate due to the following:

### Communication issues
A common reason for avoiding collaboration is communication difficulties driven by the organization's size or internal politics. When teams have a hard time collaborating and agreeing it may be more cost-effective to go their separate ways and duplicate functionality in multiple bounded contexts.

### Generic Subdomains
The nature of the duplicated subdomain can also be a reason for the teams to go their separate ways when the subdomain in question is generic, and if the generic solution is easy to integrate it may be more cost-effective to integrate it locally in each bounded context, an example is a logging framework it would make little sense for one of the bounded contexts to expose it as a service, the added complexity of integrating such a solution would outweigh the benefit of not duplicating the functionality in multiple contexts. Duplicating the functionality would be less expensive than collaborating

### Model Differences 
Differences in the bounded contexts models can also be a reason to go with a separate way of collaboration the models may be so different that a conformist relationship is impossible and implementing an anticorruption layer would be more expensive than duplicating the functionality in such a case it is again more cost-effective for the teams to go their separate ways


> [!NOTE] When separate ways pattern also should be avoided 
> it should be avoided when integrating core subdomains. Duplicating the implementation of such subdomains would defy the company's strategy to implement them in the most effective and optimized way

## Context Map 

when analyzing the integration pattern between a system's bounded contexts we can plot them on a context map 
![[Screenshot 2024-02-24 at 08.56.42.png]]

the context map is a visual representation of the system's bounded context and the integration between them. this visual notation gives valuable strategic insight on multiple levels 
- High-level design 
	- a context map provides an overview of the system's components and the models they implement
- communication patterns
	- a context map depicts the communication patterns among teams for example which teams are collaborating and which prefer less intimate integration patterns such as the anticorruption layer an separate ways patterns. 
- organizational issues
	- a context map can give insight into organizational issues, for example what does it mean if a certain upstream team's downstream consumers all resort to implementing an anticorruption layer.
### Maintenance
Ideally, a context map should be introduced in a project right from the get-go and be updated to reflect additions of new bounded contexts and modifications to the existing one.
A context map can be managed and maintained as code using tool like context mapper

### Limitations 
it's important to note that charting a context map can be a challenging task when a system's bounded contexts encompass multiple subdomains there can be multiple integration patterns at play, even if bounded contexts are limited to a single subdomain there still can be multiple integration patterns at play - for example, if the subdomains modules require different integration strategies.
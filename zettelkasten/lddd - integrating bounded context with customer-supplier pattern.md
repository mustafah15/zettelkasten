---
tags:
  - book-notes
  - ddd
related: "[[lddd - integrating bounded contexts]]"
type:
  - literature
---

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

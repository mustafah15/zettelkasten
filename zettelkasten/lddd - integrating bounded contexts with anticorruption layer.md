---
tags:
  - book-notes
  - ddd
related: "[[lddd - integrating bounded context with customer-supplier pattern]]"
type:
  - literature
aliases:
  - anti-corruption layer
---
### Anticorruption Layer
As we are still in the [[lddd - integrating bounded context with customer-supplier pattern|customer-supplier pattern]] and if the balance of power is still toward the upstream service as in the [[lddd - integrating bounded contexts with conformist pattern|conformist]] case, however, in this case, the downstream bounded context is not willing to conform instead it can translate the upstream bounded context's model into a model tailored to its own needs via an anticorruption layer as shown below 

![[Screenshot 2024-02-24 at 07.34.56.png]]

The anti-corruption layer pattern addresses scenarios in which it is not desirable or worth the effort to conform to the supplier's model such as the following:
- when the downstream bounded context contains a core subdomain
	- a core subdomain model requires extra attention and adhering to the supplier's model might impede the modeling of the problem domain.
- when the upstream model is insufficient or inconvenient for the consumer's need
	- if a bounded context conforms to a mess it risks becoming a mess itself
- when the supplier's contract changes often
	- the consumer wants to protect its model from the frequent changes
from a modeling perspective, the translation of the supplier's model isolates the downstream consumer from foreign concepts that are not relevant to its bounded context hence it simplifies the consumer's ubiquitous language and model.

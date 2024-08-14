---
tags:
  - book-notes
  - ddd
related: "[[lddd - integrating bounded context with customer-supplier pattern]]"
type:
  - literature
aliases:
  - open-host service pattern
---
### Open Host Service 
This pattern is the final type of [[lddd - integrating bounded context with customer-supplier pattern]] as this addresses the case in which the power is skewed toward the consumers the supplier is interested in protecting its consumers and providing the best service possible. 

to protect the consumers from changes in its implementation model the upstream supplier decouples the implementation model from the public interface, this decoupling allows the supplier to evolve its implementation and public models at different rates. 
![[Screenshot 2024-02-24 at 07.56.18.png]]

the supplier public interface is not intended to conform to its ubiquitous language instead it is intended to expose a protocol convenient for the consumers expressed in an integration-oriented language as such the public protocol is called the published language
in a sense, the open-host service pattern is a reversal of the [[lddd - integrating bounded contexts with anticorruption layer|anti-corruption layer]] instead of the consumer the supplier implements the translation of its internal model

Decoupling the bounded context's implementation and integration models gives the upstream bounded context the freedom to evolve its implementation without affecting the downstream contexts this is only possible if the modified implementation model can be translated into the published language the consumer already using. 

The integration model's decoupling allows the upstream bounded context to simultaneously expose multiple versions of the published language allowing the. consumer to migrate to the new version gradually 
![[Screenshot 2024-02-24 at 08.05.09.png]]

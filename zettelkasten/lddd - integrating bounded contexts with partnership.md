---
tags:
  - book-notes
  - ddd
aliases:
  - bounded context partnership
type:
  - literature
related: "[[lddd - integrating bounded context with cooperation pattern]]"
---
### Partnership

In the partnership model, the integration between bounded contexts is coordinated in an ad hoc manner one team can notify another team about a change in the API, and the second team will cooperate and adopt 

![[Screenshot 2024-02-20 at 20.43.59.png]]
The Coordination of integration here is two-way no one team dictates the language that is used for defining the contracts. The teams can work out the differences and choose the most appropriate solutions also both sides cooperate in solving any integration issues that might come up neither team is interested in blocking the other one. 
high levels of commitment and frequent synchronization between teams are **required** for successful integration in this manner 
This Pattern might not be a good fit for geographically distributed teams since it may present synchronization and communication challenges. also might be hard for two different teams in different companies to work on such a model.
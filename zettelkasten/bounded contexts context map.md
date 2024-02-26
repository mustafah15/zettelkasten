---
tags:
  - book-notes
  - ddd
type:
  - literature
aliases:
  - Context Map
related: "[[lddd - integrating bounded contexts]]"
---

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
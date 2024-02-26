---
tags:
  - book-notes
  - ddd
related: "[[lddd - integrating bounded contexts]]"
type:
  - literature
aliases:
  - separate-ways pattern
---

## Separate Ways
This pattern can arise for different reasons in cases where the teams are unwilling to unable to collaborate due to the following:
### 1. Communication issues
A common reason for avoiding collaboration is communication difficulties driven by the organization's size or internal politics. When teams have a hard time collaborating and agreeing it may be more cost-effective to go their separate ways and duplicate functionality in multiple bounded contexts.

### 2. Generic Subdomains
The nature of the duplicated subdomain can also be a reason for the teams to go their separate ways when the subdomain in question is generic, and if the generic solution is easy to integrate it may be more cost-effective to integrate it locally in each bounded context, an example is a logging framework it would make little sense for one of the bounded contexts to expose it as a service, the added complexity of integrating such a solution would outweigh the benefit of not duplicating the functionality in multiple contexts. Duplicating the functionality would be less expensive than collaborating

### 3. Model Differences 
Differences in the bounded contexts models can also be a reason to go with a separate way of collaboration the models may be so different that a conformist relationship is impossible and implementing an anticorruption layer would be more expensive than duplicating the functionality in such a case it is again more cost-effective for the teams to go their separate ways

> [!NOTE] When separate ways pattern also should be avoided 
> it should be avoided when integrating core subdomains. Duplicating the implementation of such subdomains would defy the company's strategy to implement them in the most effective and optimized way


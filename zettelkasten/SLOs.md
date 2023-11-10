---
tags:
  - SRE
type:
  - fleeting
related: "[[observability]]"
aliases:
  - service level objectives
---
An SLO (service level objective) is an agreement within  [[SLAs]] about a specific metric like uptime or response time. So, if the [[SLAs]] is the formal agreement between you and your customer, SLOs are the individual promises you’re making to that customer. SLOs are what set customer expectations and tell IT and DevOps teams.

### The challenges of SLOs

SLOs get less hate than SLAs, but they can create just as many problems if they’re vague, overly complicated, or impossible to measure. The key to SLOs that don’t make your engineers want to tear their hair out is simplicity and clarity. Only the most important metrics should qualify for SLO status, the objectives should be spelled out in plain language, and, as with SLAs, they should always account for issues such as client-side delays.


### Who needs SLOs?

Where SLAs are only relevant in the case of paying customers, SLOs can be useful for both paid and unpaid accounts, as well as internal and external customers. 
Internal systems, such as CRMs, client data repositories, and intranet, can be just as important as external-facing systems. And having SLOs for those internal systems is an important piece of not only meeting business goals but enabling internal teams to meet their own customer-facing goals.
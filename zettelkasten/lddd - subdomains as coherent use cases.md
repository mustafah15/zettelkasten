---
tags:
  - book-notes
  - ddd
related: "[[lddd - identifying subdomain boundaries]]"
type:
  - fleeting
aliases:
  - subdomains as coherent use cases
---


### subdomains as coherent use cases 
from a technical perspective, subdomains resemble sets of interrelated coherent use cases. such sets of use cases usually involve the same actor, the business entities and they all manipulate a closely related set of data
we can use the definition of "subdomains as a set of coherent use cases" as a guiding principle for when stopping looking for finer-grained subdomains.
- Should you always strive to identify such laser-focused subdomain boundaries?
- It's necessary for the core subdomains. core subdomains are the most important volatile and complex. We must distill them as much as possible since that will allow us to extract all generic and supporting functionalities and invest the effort on a much more focused functionality 
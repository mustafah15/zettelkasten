---
tags:
  - book-notes
  - ddd
related: "[[lddd -  analyzing business domains]]"
type:
  - literature
aliases:
  - identifying subdomain boundaries
---



## Identifying subdomain boundaries 
subdomains and their types are defined by the company's business strategy its business domain and how it differentiates itself to compete with other companies in the same field. A good starting point is the company's departments and other organizational units for example an online retail shop might include a warehouse, customer service picking, and shipping quality control these are relatively coarse-grained areas of activity, for example, customer service department its reasonable to assume that it would be supporting or even a generic subdomain, as this function often outsourced to third party vendors but this information enough for us to make sound software design decisions?

### distilling subdomains 
coarse-grained subdomains are a good starting point, but we have to make sure we are not missing important information hidden in the intricacies of the business function, let's take our example for customer service when viewed as individual subdomains these activities can be of different types while help desk and telephone systems are generic subdomains shift management is a supporting one while a company may develop its ingenious algorithm for routing incidents to agents having success with similar cases in the past the routing algorithm requires analyzing incoming cases and identifying similarities in past experience ![[Screenshot 2024-01-25 at 09.17.59.png]]
on the other hand, we cannot drill down indefinitely looking for insights at lower and lower levels of granularity when should you stop?
### [[lddd - subdomains as coherent use cases|subdomains as coherent use cases]]

### Focus on the essentials
subdomains are a tool that alleviates the process of making software design decisions. All organizations likely have a quite few business functionalities that drive their competitive advantage but have nothing to do with software.
When looking for subdomains it's important to identify business functions that re not related to software, acknowledge them as such, and focus on aspects of the business that re relevant to the software system you are working on.


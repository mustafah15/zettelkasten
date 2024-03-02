---
tags:
  - book-notes
  - ddd
type:
  - literature
aliases:
  - Bounded Contexts Vs Subdomains
related: "[[lddd - managing domain complexity]]"
---

At first, the two methods of decomposing the business domain might seem redundant, however, that is not the case, we will show why we need both boundaries 
### subdomains 
According to DDD methodology, the analysis phase involves identifying the different subdomains (core, supporting, and generic), that's how the organization works and plans its competitive strategy, a subdomain resembles a set of interrelated use cases the use case is defined by the business domain and the system's requirements. As software engineer, we don't define the requirement instead we are analysing the business domain to identify the subdomains. 
### Bounded Contexts
Bounded Contexts on the other hand are designed, choosing models' boundaries is a strategic design decision. we decide how to divide the business domain into smaller manageable problem domains. 

### The interplay between subdomains and bounded context 
Theoretically, though impractically a single model could span the entire business domain this strategy could work for a small system
![[Screenshot 2024-02-08 at 08.31.31.png]]
when conflicting models arise, we can follow the domain experts' mental models and decompose the systems into bounded contexts
if the models are still large and hard to maintain we can decompose them into even smaller bounded contexts for example by having a bounded context for each subdomain.
Either way, this is a design decision we design those boundaries as a part of the solution, Having a one-to-one relationship between bounded contexts and subdomains can be perfectly reasonable in some scenarios. in others however different decomposition strategies can be more suitable.

- It's very important to remember that subdomains are discovered and bounded contexts are designed 
- the business strategy defines the subdomains. 
however, we can design the software solution and its bounded context to address the specific project context and constraints As a model is intended to solve a specific problem in some cases it can be beneficial to use multiple models of the same concept simultaneously to solve different problems, as different types of maps provide different type of information about our planet.
Limiting the design to one-to-one relationships between bounded contexts would inhibit this flexibility and force us to use a single model of a subdomain in its bounded context.


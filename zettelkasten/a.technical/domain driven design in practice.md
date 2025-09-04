---
tags:
  - software-design
  - ddd
type: fleeting
related: "[[domain driven design]]"
---
### When to use domain-driven design?

when you have a big business logic complexity in your application, other than that, it will lead to over-engineering, an example for that will be an enterprise-level applications the biggest challenge in such projects is to handle business logic complexity in such a way that it would be possible to extend and maintain the solution in the long run that is exactly the task that the domain driven design practices are aimed to solve, they help us create code which not only fully powers the problem but also does it in the simplest and most maintainable way possible.

### Why Domain-Driven Design?

There are two core principles in software development to which every programmer should adhere in most cases. 
- YAGNI (you are not gonna need it): This means you should only implement the functionality you need in this particular moment, and you shouldn't try to anticipate the future needs.
- KISS(keep it short and simple): This means making the implementation of the functionality as simple as possible, the simple your code is the more readable and thus more maintainable it becomes.

DDD and its practices complement these two software development principles, and it allows us to extract the central part of the problem domain and simplify it, and gives us the ability to express business logic in the clearest way possible is a single trait that makes DDD so appealing in enterprise-level applications. 
As the most difficult task in the modern business line software is to keep their complexity under control [[complexity in software design]]

There is a limit to the complexity that we can deal with. If the code exceeds it, it becomes really hard to change anything in the software without introducing some unexpected side effects. Extending such a project becomes a pain and usually results in a lot of bugs.

The uncontrollable growth of complexity is one of the biggest reasons why software projects fail. [[complexity is incremental]]


### Strategic Elements of DDD

- [[ubiquitous language]]
- [[what is a bounded context|bounded context]]
- [[core subdomain]]


### Onion Architecture 

onion architecture emphasized the fact that the core part of the structure can not depend on anything else except itself which means that the core elements of our domain model should act in isolation from others. any other layer should only depend on the layer under it
![[Screenshot 2025-02-16 at 19.44.43.png]]



## Vocabulary Used

### core domain 

[[core subdomain]] is the essential part of the problem domain, which can't be delegated to external solutions and must be resolved by us developers.

### Domain 
is the problem we are working on 

### Domain Model 
is the solution for the problem and how we model it inside our code or solution.



## Problem Description

building a vending machine program 
we should be able to perform the following 
- insert money into the machine 
- return the money back
- buy a snack

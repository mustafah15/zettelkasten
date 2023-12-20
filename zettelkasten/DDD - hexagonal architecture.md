---
tags:
  - ddd
  - software-design
type:
  - literature
related: "[[domain driven design]]"
---

Also known as ports and adapters, it's an alternative to the layered or N-tier architecture

- Domain is isolated to the center of the model, and becomes the architectural focus.
- ports are exposed as an API for the domain
- infrastructure contains adapters that map to the ports.
- Hexagonal architecture can be viewed as an onion.
- the domain is in the center, API provides interface to the domain, these are your ports.
- infrastructure adapts incoming and outgoing traffic into the ports.
- outer layer depend on inner layers.
- inner layer have no knowledge of the outer layers.
- Hexagonal Architecture ensures proper separation of infrastructure from Domain.
- Prevents concerns around databases, user interfaces etc, from bleeding into the domain.
- can be enforced with package, or even project structure in the application allows your domain portable.
![[arch.png]]
## Implementing DDD

example on the folder structure for the hexagon architecture
the request is handled by a controller who use a mapper to map the request to a domain object and then pass it to the service which do the required job for the request and return the response to the controller to replay the request

the service it self use the domain object and use other infra structure objects to be able to do it's job.![[arch1.png]]
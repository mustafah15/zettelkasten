---
tags:
  - platform-engineering
type: literature
---

## What is Platform Engineering 

platform engineering is the discipline of designing and building toolchains and workflows that enable self-service capabilities for software engineering organizations. 

## Why do Companies need platform engineering teams?

- Before DevOps
	- Dev teams send deployable packages to ops teams waiting until deployment to happen depending on ops teams' schedule. 
	- If deployment has issues because of the code the Ops teams would wait for dev teams to fix it.
	- slow communication between ops and dev teams lead to slow delivery 
- DevOps Introduction 
	- combine dev and ops in one team, less communication challenges.
	- "You build it you run it"
- problems with DevOps
	- High Cognitive Load on Engineers as they own the whole stack
	- Different Solutions for the same problem in the same company 
- Internal Developer Platform Introduction 
	- Formal Definition: A set of tools and tech that a platform engineering team binds together into a golden path to enable developer self-service. 
	- **Internal**: clearly separated from externally facing platforms, IDPs are meant for internal use only.
	- **Developer** – indicates the internal customer and the primary user, the application developer.
	- **Platform** – characterizes the product type
- Why Internal Platform?
	- Providing Developers with self-service option and at the same time driving standardization IDPs boost developer productivity and developer experience through a reduction in waiting time or manual work for operations. 
	- Every company/team has their own needs for IDP
- How IDP help teams to build and **innovate** faster
	- DEVEOPER CONTROL PLANE
	- INTEGRATION DELIVERY PLANE
	- RESOURCE PLANE
	- SECURITY PLANE
	- OBSERVABILITY PLANE
	- 
	- building a platform layer on top of the infrastructure that product teams can use without going deep into
	- having a shared solution for common problems. 
	- Building a base for Product teams to use so they can kick-start their work directly without starting from scratch.
 
- platform as a product (PAAP)
	- thoughtworks tech radar 2017 and then was popularized among the broader audiencece in team topologies book
	- in this context platform as a product means building a platform that is customer focused with product teams as the primary customers of the platform having platform engineering teams take ownership of the core functionality of the platform layer. 
	- following a (PAAP) mindset, the platform built by the internal platform team competes against other solutions, platform teams needs to start everything based on user research check engineers pain points and figure out what they really need, you need to identify what tasks that causes most pain and try to fix these issue to have better developer experience 

resources and links:
- https://www.youtube.com/@PlatformEngineering
- https://internaldeveloperplatform.org/
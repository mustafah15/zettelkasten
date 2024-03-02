---
tags:
  - software-design
  - ddd
related: 
type:
  - literature
---

Domain Driven design originates from a book called Domain Driven Design by Eric Evans.
One of the key goals of the book is to try **to create a software implementation that is based on an evolving model that is understood by the domain experts.** so largely about creating a communication channel between the domain experts and the software developers.
As far as goals go for domain driven design one of the key goals within it is to take a large system, or a large domain and to break it down to smaller pieces. the problem that we have the larger domain you have the more harder you can deal with it and harder to model a a large singe coherent model.
break things down into small pieces. this gives us a way to determine the boundaries, essentially between those smaller pieces within the larger domain,
Reactive micro-services for example have a similar goal they need to be separated along clear boundaries, each microservice has to have a clearly defined api and a specific set of responsibilities. if we don't know what the responsibilities of the microservice it's going to be very hard to build it and have a proper design for it.
thats where the DDD will help us it give us a set of guidelines and a set of techniques that we can use to try to help us to break larger domain into a smaller ones.
### What Is a Domain?
- A domain in the context of the software, it refers to the business or idea that we are modeling.
- Experts in the domain are people who understand the business, not necessarily the software.
- the Key goal of DDD is to build a model that the domain experts understand, and the model is not the software.
	- the model represents our understanding of the domain.
	- the software is an implementation of the model.

Business domain: The business domain define a company's main area of activity, it's the service the company provides to its clients for example. 
	- FedEx provides courier delivery
	- walmart is a retail establishment 
a company can operate in multiple business domains for example amazon, it's also important to note that companies can change their business domains 

### Decomposing the domain
- take the large domain and separate them into subdomains, our subdomains are created by grouping related ideas and actions and rules into separate domains.
- because of that each subdomain essentially ends up having its own [[lddd - ubiquitous language]] and model. The language and model for a subdomain is what we call a [[DDD - bounded context|bounded context]],** subdomain or Bounded contexts are good starting points for building reactive microservices.
- from one Bounded context to the next the meaning of a word may change dramatically.
	- in restaurant, when talking to a server, an order, has a very specific meaning.
	- when we speaking to the person who manage inventory for the restaurant order means something completely different.

### How to determine bounded context
- here you are some guidelines because there are no universal answer
	- consider human culture and interaction
	- Different areas of the domain that are handled by different groups of people, suggests a natural division.
	- look for changes in ubiquitous language
	- if the use of language or the meaning of that language changes, that may suggest a new context.
	- look for varying or unnecessary information
	- employee id is very important in an employee, meaningless in a customer.
	- strongly separated bounded context will result in smooth workflows.
		- an awkward workflow may signal a misunderstanding of the domain.
		- if a bounded context has too many dependencies it may be overcomplicated.
### Event First Domain Driven Design 
- Traditionally DDD focused on the objects within the domain
	- Cook, Reservation, Customer...

- Event First Domain Driven Design Places the focus on the activities or events that occur in the domain
	- customer makes a reservation, server places an order, food is served to the customer.
	- using event first DDD we start by defining the activities, then group those activities to find logical system boundaries

### Maintaining purity of boundaries 
 Maintaining the purity of those bounded contexts needs a technique or a set of techniques that allows us to do that.
### Anti-Corruption Layers

Each Bounded context may have domain concepts that are unique, Concepts are not always compatible from one context to the next.

- Anti-corruption layers are introduced to translate these concepts
- Anti-corruption layers will prevent Bounded context from leaking into each other.
- Anti-corruption layers help the bounded context to stand alone.

### **How Anti Corruption Layers are implemented**
a common way to build it is abstract interface that represent pure domain representation of the data and then we have implementation of this interface which dose that translation and that sort of infrastructure component that dose that translation.

### Anti-Corruption Layers for Legacy systems

the domain for the legacy system maybe messy or unclear, but the Anti-Corruption layer keeps your Bounded Context pure.
It prevents your domain from dealing with the mess of the legacy system.

### Context Maps
![[Screenshot 2023-09-02 at 19.40.03.png]]
- Context Maps are a way of visualizing Bounded Contexts and the relationships between them.
- Bounded Contexts are drawn as simple shapes
- lines connect the Bounded Contexts to indicate relationships
- Lines may be labeled to indicate the nature of the relationships


## [[DDD - bounded context]]
## [[DDD - domain activities]] 
## [[DDD - domain abstraction]]
## [[DDD - domain objects]]
## [[DDD - hexagonal architecture]]

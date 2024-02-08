---
tags:
  - book-notes
  - ddd
related: "[[learning domain driven design]]"
type:
  - fleeting
---
to ensure a project's success you must develop a ubiquitous language that can be used for communication by all stakeholders, the language should reflect the domain experts' mental models of the business domain's inner workings and underlying principles. since our goal is to use ubiquitous language to drive software design decisions the language must be clear and consistent. it should be free of ambiguity, implicit assumptions, and extraneous details. however, on an organisational scale, the domain experts' mental models can be inconsistent themselves. different domain experts can use different models of the same business domain.

## Inconsistent Models

A telemarketing company can use the term "lead" in a different meaning in the marketing and sales departments:
Marketing department 
- for the marketing people, a lead represents a notification that somebody is interested in one of the products. 
Sales Department 
- In the context of the sales department a lead is a much more complex entity. it represents the entire lifecycle of the sales process it's not a mere event but a long-running process.
How do we formulate a ubiquitous language in the case of this company?
- on one hand, we know the ubiquitous language has to be consistent each term should have one meaning, and on the other hand, we know the ubiquitous language has to reflect the domain experts' mental models. In this case the mental model of the "lead" is consistent among the domain experts in the sales and marketing departments. 
- it might be easy enough for humans to infer the exact meaning from the interaction's context but it is more difficult to represent such a divergent model of the business domain in software. source code doesn't cope well with ambiguity.
How we solve this catch?
- the traditional solution to this problem is to design a single model that can be used for all kinds of problems. such models result in enormous entity relationship diagrams which are not an effective model, such models are supposed to be suitable for everything but eventually are effective for nothing, as in such models you are always facing complexity (the complexity of filtering out extraneous details, the complexity of finding what you need and most importantly the complexity of keeping the data in a consistent state)
- another solution would be to prefix the problematic term with a definition of the context "marketing lead" and "sales lead". that would allow the implementation of the two models in the code. this approach has two main disadvantages. first, it includes [[cognitive load]] when should each model be used? the closer the implementations of the conflicting models are the easier it is to make a mistake. second, the implementation of the model won't be aligned with the ubiquitous language. no one would use the prefixes in a conversation. people don't need this extra information they can rely on the conversation context
- a domain driven design solution for solving such scenarios is the [[DDD - bounded context|bounded context]]

## What is a Bounded Context?

The solution in domain-driven design is trivial: divide the ubiquitous language into multiple smaller languages, then assign each one to the explicit context in which it can be applied: **its bounded context**

As we Identified two bounded contexts (marketing and sales) the term lead exists in both bounded contexts, each fine-grained ubiquitous language is consistent and follows the domain experts' mental models.
In a sense, terminology conflicts and implicit contexts are an inherent part of any decent-sized business. with the bounded context pattern, the contexts are modeled as an explicit and integral part of the business domain.

![[Screenshot 2024-02-07 at 07.57.18.png]]


### Model Boundaries

as we know that a model is not a copy of the real world but a construct that helps us make sense of a complex system. The problem it is supposed to solve is an inherent part of a model its purpose. A model cannot exist without a boundary; it will expand to become a copy of the real world. that makes defining a model boundary - its bounded contexts - an intrinsic part of the modeling process. 
just as a subway map is useless for nautical navigation, a ubiquitous language in one bounded context can be completely irrelevant to the scope of another bounded context.
Bounded contexts define the applicability of a ubiquitous language and of the model it represents, in other words, bounded contexts are the consistency boundaries of a ubiquitous language. A language's terminology principles and business rules are only consistent inside its bounded context.

### Ubiquitous Language Refined 
ref:  [[ubiquitous language]]
a ubiquitous language is not "ubiquitous" in the sense that it should be used and applied "ubiquitous" throughout the organization. a ubiquitous language is **not** universal. 
Instead, a ubiquitous language is ubiquitous only in the boundaries of its bounded context the language is focused on describing only the model that is encompassed by the bounded context. As a model cannot exist without a problem it is supposed to address, a ubiquitous language cannot be defined or used without an explicit context of its applicability.

### Scope of a Bounded Context 
Since different domain experts can hold conflicting mental models of the same business entity to model the business domain, we had to divide the model and define a strict applicability context for each fine-grained model - its bounded context
The consistency of the ubiquitous language only helps to identify the widest boundary of the language it cannot be any larger, because then there will be inconsistent models and terminology. However, we can still further decompose the models into even smaller bounded contexts, defining the scope of a ubiquitous language and its bounded context is a strategic design decision
![[Screenshot 2024-02-08 at 07.37.09.png]]

#### bounded context sizing 
a bounded context's size by itself is not a deciding factor, models shouldn't necessarily be big or small. models need to be useful. the wider the boundary of the ubiquitous language is the harder it is to make it consistent. it may be beneficial to divide a large ubiquitous language into a smaller, more manageable problem domain but striving for domain-bounded context can backfire too. the smaller they are the more integration overhead the design induces.
The reason for extracting finger-grained bounded context out of a larger one includes constituting new software engineering teams or addressing some of the system's non-functional requirements; for example, when you need to separate the development lifecycle of some of the components originally residing in a single bounded context pendently from the rest of the bounded context's functionalities. one thing to beware of is splitting a coherent functionality into multiple bounded contexts such division will hinder the ability to evolve each context independently. instead the same business requirements and changes will simultaneously affect the bounded contexts and require simultaneous deployment of changes to avoid such ineffective decomposition, use the rule of thumb ( to find subdomains identify sets of coherent use cases that operate on the same data, and avoid decomposing them into multiple bounded contexts )

## Bounded Contexts Vs Subdomains 

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


## Boundaries 
the bounded context pattern is the domain-driven design tool for defining physical and ownership boundaries.

### Physical Boundaries 

Bounded contexts serve not only as model boundaries but also as physical boundaries of the systems implementing them, each bounded context should be implemented as an individual service/project, meaning it is implemented, evolved, and versioned independently of the other bounded contexts
clear physical boundaries between bounded contexts allow us to implement each bounded context with the technology stack that best fits its needs.

A bounded context can contain multiple subdomains in such a case the bounded context is a physical boundary while each of its subdomains is a logical boundaries that bear different names in different programming languages (namespaces, modules, or packages)

### Ownership boundaries 
In software projects, we can leverage model boundaries aka bounded contexts for the peaceful coexistence of teams. the division of work between teams is another strategic decision that can be made using the bounded context pattern.
A Bounded context should be implemented, evolved, and maintained by one team ONLY. no two teams can work in the same bounded context this segregation eliminates implicit assumptions that teams might make about one another's models. instead, they have to define communication protocols for integrating their models and systems explicitly. 

> [!note]+
> It's important to note that the relationship between teams and bounded context is one-directional: a bounded context should be owned by only one team, however a single team can own multiple bounded contexts
> 

## Bounded Contexts in Real Life

bounded contexts are not as evident as business domains and subdomains but they are there as domain experts' mental models are, you just have to be conscious of how domain experts think about the different business entities and processes.

### Semantic Domains

It can be said that domain-driven design's bounded contexts are based on the lexicographical notion of [semantic domains](https://en.wikipedia.org/wiki/Semantic_domain#:~:text=In%20lexicography%20a%20semantic%20domain,%2C%20raindrop%2C%20puddle.%22.) A semantic domain is defined as an area of meaning and the words used to talk about it, for example the word monitor, port, and processor have different meaning in the software and hardware engineering semantic domains.


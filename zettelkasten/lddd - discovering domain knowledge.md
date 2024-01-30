---
tags:
  - book-notes
  - ddd
related: "[[learning domain driven design]]"
type:
  - fleeting
aliases:
  - discovering domain knowledge
---
this chapter continues the topic of [[lddd -  analyzing business domains]] but in a different dimension: depth it focuses on what happens inside a subdomain, its business function, and logic. 

## business problem 
the software systems we are building are just solutions to business problems. In this context, the word problem does not resemble a mathematical problem or a riddle that you broader meaning a business problem can be challenges associated with optimizing workflows and processes, minimizing manual labor managing resources, supporting decisions managing data, and so on. Business problems appear both at the business domain and subdomain levels. A company's goal is to provide a solution for its customer's problems.

## knowledge discovery
To design an effective software solution, we have to grasp at least the basic knowledge of the business domain. the knowledge belongs to [[lddd - who are the domain experts|domain experts]] as it's their job in the first place, and it's crucial for us to understand domain experts and to use the same business terminology they use.
to be effective the software has to mimic the domain experts' way of thinking about the problem and their mental model. without an understanding of the business problem and the reasoning behind the requirements, our solutions will be limited to "translating" business requirements to code. and what if the requirements miss a crucial edge case? or fail to describe a business concept, limiting our ability to implement a model that will support future requirements? 
Effective knowledge sharing between domain experts and software engineers requires effective communication.

## communication
it's safe to say that almost all software projects require the collaboration of stakeholders in different roles (domain experts, product owners, engineers, designers) as in any collaborative effort the outcome depends on how well all those parties can work together. for example, do all stakeholders agree on what problem is being solved? what about the solution they are building do they hold any conflicting assumptions about its functional and non-functional requirements? agreement and alignment on all project-related matters are essential to a project's success.
yet despite the importance of effective communication in the project success, it is rarely observed in software projects, often businesspeople and engineers have no direct interaction with one another, instead domain knowledge is pushed down from domain experts to engineers, and it is delivered through people playing the role as mediators or translators systems/business analysts or product owners. 
during this traditional software development lifecycle, the domain knowledge is translated into an engineer-friendly form known as an analysis model, which is a description of the system requirements rather than an understanding of the business domain behind it. such mediation is hazardous to knowledge sharing because in any translation there's information is lost and in this case, it is domain knowledge that is essential for solving business problems. also often these documents got out of date quickly. 


## [[ubiquitous language|what is ubiquitous language]]

## Language of the business
it's crucial to emphasize that the [[ubiquitous language]] is the language of the business as such, it should consist of business domain-related terms only. no technical jargon Teaching business domain experts about singletons and abstract factories is not your goal the ubiquitous aims to frame the domain experts understanding and mental models of the business domain in terms that are easy to understand. 

### Scenarios 
consider the following statements 
- An advertising campaign can display different creative materials. 
- a campaign can be published only if at least one of its placements is active. 
- sales commissions are accounted for after transactions are approved. 
All these statements are formulated in the language of the business that is they reflect the domain experts' view of the business domain. 
### Consistency 
The [[ubiquitous language]] must be precise and consistent. it should eliminate the need for assumptions and should make the business domain logic explicit 
since ambiguity hinders communication, each term of the [[ubiquitous language]] should have one and only one meaning, here are a few examples of unclear terminology and how it can be improved. 

#### ambiguous terms
Let's say that in some business domains, the term policy has multiple meanings it can mean a regulatory rule or an insurance contract. the exact meaning can be worked out in human-to-human interaction depending on the context. software however does not cope well with ambiguity and it can be cumbersome and challenging to model the "policy" entity in code. 
[[ubiquitous language]] demands a single meaning for each term so "policy" should be modeled explicitly using two terms **regulatory rule** and **insurance contract**.

#### synonymous terms
two terms cannot be used interchangeably in a [[ubiquitous language]]. for example, many systems use the term **user** however a careful examination of the domain experts' lingo may reveal that user and other terms are used interchangeably for example user, visitor, and account.
synonymous terms can seem harmless at first however in most cases they contain different concepts in this example both visitor and account technically refer to the system's user however in most systems unregistered and registered users represent different roles and have different behaviours. for example, the "visitors" data is used mainly for analysis purposes whereas "accounts" actually use the system and its functionality 
so it is preferable to use each term explicitly in its specific context. Understanding the difference between the terms in use allows for building simpler and clearer models and implementations of the business domain entities.

## What is a model?
A model is not a copy of the real world but a human contract that helps us make sense of real-world systems.

A canonical example of a model is a map. Any map is a model including navigation maps, terrain maps world maps....
none of these maps represents all the details of our plants. instead, each map contains just enough data to support its particular purpose: the problem it is supposed to solve.

### Effective Modeling 
All models have a purpose and an effective model contains only the details needed to fulfill its purpose. for example, you won't see subway stops on a world map. On the other hand, you cannot use a subway map to estimate distances. Each map contains just the information it is supposed to provide. 

In its essence, a model is an abstraction the notion of abstraction allows us to handle complexity by omitting unnecessary details and leaving only what is needed to solve the problem at hand 

### Modeling the business domain
When cultivating a [[ubiquitous language]], we are effectively building a model of the business domain. The model should capture the domain experts' mental models about how the business works to implement its function.
the [[ubiquitous language]] we use is not supposed to cover every possible detail of the domain. that would be equivalent to making every stakeholder a domain expert. instead, the model is supposed to include just enough aspects of the business of the business domain to make it possible to implement the required system.
Effective communication between engineering teams and domain experts is vital the importance of this communication grows with the complexity of the business domain. the more complex the business domain is the harder it to implement its business logic in the code even if a slight misunderstanding will inadvertently lead to an implementation prone to severe bugs. the only reliable way to verify a business domain's understanding is to converse with domain experts and do it in the language they understand (the language of the business).

#### Continuous effort
Formulation of a [[ubiquitous language]] requires interaction with its natural holders, the domain experts. Only interaction with actual domain experts can uncover wrong assumptions or an overall flawed understanding of the business domain. 
All stakeholders should consistently use the [[ubiquitous language]] in all project-related communication to spread knowledge about and foster a shared understanding of the project, tests, documentation and even the source code itself should use this language. 
Most importantly cultivation of a ubiquitous language is an ongoing process. it should be constantly validated and evolved. everyday use of the language will over time reveal deeper insights into the business domain.

#### Tools
There are tools and technologies that can alleviate the process of capturing and managing a [[ubiquitous language]]
- A wiki can be used as a **glossary** to capture and document the language. such a glossary allocates the onboarding process of new team members as it serves as a go-to place for information about the business domain terminology.
- uses cases or Gherkin Automated tests written in the Gherkin language are not only great tools for capturing the [[ubiquitous language]] but also act as an additional tool for bridging the gap between domain experts and software engineers, for example
```Gherkin
Scenario: Notify the agent about a new support case
	Given: Vincent Jules submits a new support case saying: 
	"""
		I need help configuring AWS Infinidash
	"""
	When the ticket is assigned to Mr.Wolf
	Then the agent receives a notification about the new ticket
```
Managing a Gherkin-based test suite can be challenging at times, especially at the early stages of a project, however, it is definitely worth it for complex business domains.
use the tools to support the management of the [[ubiquitous language]] but don't expect the documentation to replace the actual usage. "individuals and interactions over processes and tools"

#### Challenges
In theory, cultivating a [[ubiquitous language]] sounds like a simple, straightforward process. In practice it isn't the only reliable way to gather domain knowledge is to converse with domain experts 
As you gain experience in this practice you will notice that frequently this process involves not just discovering knowledge that is already there but rather co-creating the model in tandem with domain experts.
you may encounter business domain concepts that lack explicit definition, and asking questions about the nature of the business domain often makes such implicit conflicts and white spots explicit this is especially common for core subdomains. in such a case, the learning process is mutual you are helping the domain experts better understand their field, 

The question about the [[ubiquitous language]] that is frequently asked is what language should we use if the company is not an English speaking country so the answer is at least use English nouns for the naming business domain entities, this will alleviate using the same terminology in code

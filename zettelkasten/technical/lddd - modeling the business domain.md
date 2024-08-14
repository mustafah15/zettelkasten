---
tags:
  - book-notes
  - ddd
related: "[[lddd - converting business domain to a model]]"
type:
  - literature
---
### Modeling the business domain
When cultivating a [[lddd - ubiquitous language]], we are effectively building a model of the business domain. The model should capture the domain experts' mental models about how the business works to implement its function.
the [[lddd - ubiquitous language]] we use is not supposed to cover every possible detail of the domain. that would be equivalent to making every stakeholder a domain expert. instead, the model is supposed to include just enough aspects of the business of the business domain to make it possible to implement the required system.
Effective communication between engineering teams and domain experts is vital the importance of this communication grows with the complexity of the business domain. the more complex the business domain is the harder it to implement its business logic in the code even if a slight misunderstanding will inadvertently lead to an implementation prone to severe bugs. the only reliable way to verify a business domain's understanding is to converse with domain experts and do it in the language they understand (the language of the business).

#### Continuous effort
Formulation of a [[lddd - ubiquitous language]] requires interaction with its natural holders, the domain experts. Only interaction with actual domain experts can uncover wrong assumptions or an overall flawed understanding of the business domain. 
All stakeholders should consistently use the [[lddd - ubiquitous language]] in all project-related communication to spread knowledge about and foster a shared understanding of the project, tests, documentation and even the source code itself should use this language. 
Most importantly cultivation of a ubiquitous language is an ongoing process. it should be constantly validated and evolved. everyday use of the language will over time reveal deeper insights into the business domain.

#### Tools
There are tools and technologies that can alleviate the process of capturing and managing a [[lddd - ubiquitous language]]
- A wiki can be used as a **glossary** to capture and document the language. such a glossary allocates the onboarding process of new team members as it serves as a go-to place for information about the business domain terminology.
- uses cases or Gherkin Automated tests written in the Gherkin language are not only great tools for capturing the [[lddd - ubiquitous language]] but also act as an additional tool for bridging the gap between domain experts and software engineers, for example
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
use the tools to support the management of the [[lddd - ubiquitous language]] but don't expect the documentation to replace the actual usage. "individuals and interactions over processes and tools"

#### Challenges
In theory, cultivating a [[lddd - ubiquitous language]] sounds like a simple, straightforward process. In practice it isn't the only reliable way to gather domain knowledge is to converse with domain experts 
As you gain experience in this practice you will notice that frequently this process involves not just discovering knowledge that is already there but rather co-creating the model in tandem with domain experts.
you may encounter business domain concepts that lack explicit definition, and asking questions about the nature of the business domain often makes such implicit conflicts and white spots explicit this is especially common for core subdomains. in such a case, the learning process is mutual you are helping the domain experts better understand their field, 

The question about the [[lddd - ubiquitous language]] that is frequently asked is what language should we use if the company is not an English speaking country so the answer is at least use English nouns for the naming business domain entities, this will alleviate using the same terminology in code

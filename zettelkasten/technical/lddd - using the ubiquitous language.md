---
tags:
  - book-notes
  - ddd
aliases:
  - using the ubiquitous language
related: "[[lddd - ubiquitous language]]"
type:
  - literature
---

## Language of the business
it's crucial to emphasize that the [[lddd - ubiquitous language]] is the language of the business as such, it should consist of business domain-related terms only. no technical jargon Teaching business domain experts about singletons and abstract factories is not your goal the ubiquitous aims to frame the domain experts understanding and mental models of the business domain in terms that are easy to understand. 

### Scenarios 
consider the following statements 
- An advertising campaign can display different creative materials. 
- a campaign can be published only if at least one of its placements is active. 
- sales commissions are accounted for after transactions are approved. 
All these statements are formulated in the language of the business that is they reflect the domain experts' view of the business domain. 
### Consistency 
The [[lddd - ubiquitous language]] must be precise and consistent. it should eliminate the need for assumptions and should make the business domain logic explicit 
since ambiguity hinders communication, each term of the [[lddd - ubiquitous language]] should have one and only one meaning, here are a few examples of unclear terminology and how it can be improved. 

#### ambiguous terms
Let's say that in some business domains, the term policy has multiple meanings it can mean a regulatory rule or an insurance contract. the exact meaning can be worked out in human-to-human interaction depending on the context. software however does not cope well with ambiguity and it can be cumbersome and challenging to model the "policy" entity in code. 
[[lddd - ubiquitous language]] demands a single meaning for each term so "policy" should be modeled explicitly using two terms **regulatory rule** and **insurance contract**.

#### synonymous terms
two terms cannot be used interchangeably in a [[lddd - ubiquitous language]]. for example, many systems use the term **user** however a careful examination of the domain experts' lingo may reveal that user and other terms are used interchangeably for example user, visitor, and account.
synonymous terms can seem harmless at first however in most cases they contain different concepts in this example both visitor and account technically refer to the system's user however in most systems unregistered and registered users represent different roles and have different behaviours. for example, the "visitors" data is used mainly for analysis purposes whereas "accounts" actually use the system and its functionality 
so it is preferable to use each term explicitly in its specific context. Understanding the difference between the terms in use allows for building simpler and clearer models and implementations of the business domain entities.
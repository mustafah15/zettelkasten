---
tags:
  - book-notes
  - ddd
type:
  - literature
related: "[[lddd - managing domain complexity]]"
aliases:
  - Inconsistent Models
---

Imagine a telemarketing company can use the term "lead" in a different meaning in the marketing and sales departments:
Marketing department 
- for the marketing people, a lead represents a notification that somebody is interested in one of the products. 
Sales Department 
- In the context of the sales department a lead is a much more complex entity. it represents the entire lifecycle of the sales process it's not a mere event but a long-running process.
How do we formulate a ubiquitous language in the case of this company?
- on one hand, we know the ubiquitous language has to be consistent each term should have one meaning, and on the other hand, we know the ubiquitous language has to reflect the domain experts' mental models. In this case the mental model of the "lead" is consistent among the domain experts in the sales and marketing departments. 
- it might be easy enough for humans to infer the exact meaning from the interaction's context but it is more difficult to represent such a divergent model of the business domain in software. source code doesn't cope well with ambiguity.
How we solve this catch?
- the traditional solution to this problem is to design a single model that can be used for all kinds of problems. such models result in enormous entity relationship diagrams which are not effective models, such models are supposed to be suitable for everything but eventually are effective for nothing, as in such models you are always facing complexity (the complexity of filtering out extraneous details, the complexity of finding what you need and most importantly the complexity of keeping the data in a consistent state)
- another solution would be to prefix the problematic term with a definition of the context of "marketing lead" and "sales lead". that would allow the implementation of the two models in the code. this approach has two main disadvantages. first, it includes [[cognitive load]] when should each model be used? the closer the implementations of the conflicting models are the easier it is to make a mistake. second, the implementation of the model won't be aligned with the ubiquitous language. no one would use the prefixes in a conversation. people don't need this extra information they can rely on the conversation context
- a domain driven design solution for solving such scenarios is the [[DDD - bounded context|bounded context]]
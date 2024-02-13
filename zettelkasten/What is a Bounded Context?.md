---
tags:
  - book-notes
  - ddd
aliases:
  - lddd - what is a bounded context
type:
  - literature
related: "[[lddd - managing domain complexity]]"
---

**The solution for [[lddd - inconsistent models|Inconsistent Models]] in domain-driven design is trivial: divide the ubiquitous language into multiple smaller languages, then assign each one to the explicit context in which it can be applied: **its bounded context**

As we Identified two bounded contexts (marketing and sales) the term lead exists in both bounded contexts, each fine-grained ubiquitous language is consistent and follows the domain experts' mental models.
In a sense, terminology conflicts and implicit contexts are an inherent part of any decent-sized business. with the bounded context pattern, the contexts are modeled as an explicit and integral part of the business domain.

![[Screenshot 2024-02-07 at 07.57.18.png]]

### Model Boundaries

as we know that a model is not a copy of the real world but a construct that helps us make sense of a complex system. The problem it is supposed to solve is an inherent part of a model its purpose. A model cannot exist without a boundary; it will expand to become a copy of the real world. that makes defining a model boundary - its bounded contexts - an intrinsic part of the modeling process. 
just as a subway map is useless for nautical navigation, a ubiquitous language in one bounded context can be completely irrelevant to the scope of another bounded context.
Bounded contexts define the applicability of a ubiquitous language and of the model it represents, in other words, bounded contexts are the consistency boundaries of a ubiquitous language. A language's terminology principles and business rules are only consistent inside its bounded context.

### [[lddd - scope and sizing of a bounded context|Scope and Sizing of a Bounded Context]]

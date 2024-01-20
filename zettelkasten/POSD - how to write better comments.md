---
tags:
  - book-notes
  - software-design
related: "[[philosophy of software design]]"
type:
  - literature
---
- first, a reason for writing comments is that statements in a programming language can't capture all of the important information that was in the mind of the developer when the code was written. comments should record this information so that developers who come along later can easily understand and modify the code.
	- the guiding principle for comments is that **comments should describe things that aren't obvious from the code**
	- Sometimes low-level details aren't obvious. for example, when a pair of indices describes a range, it isn't obvious whether the elements given by the indices are inside the range or out.
	- Sometimes it's not clear why code is needed, or why it was implemented in a particular way.
	- Sometimes there are rules the developer followed, such as always invoking `a` before `b` you might be able to guess a rule by looking at all of the code, but this is painful and error-prone a comment can make the rule explicit and clear.
- second, another reason for writing comments is abstractions, which include a lot of information that isn't obvious from the code. the idea of an abstraction is to provide a simple way of thinking about something but is so detailed that it can be hard to see the abstraction just from reading the code.
	- comments should provide a simpler higher-level view even if this information can be deduced by reading the code, we don't want to force users of a module to do that because reading the code is time-consuming and forces them to consider a lot of information that isn't needed to use the module.
	- A developer should be able to understand the abstraction provided by a module without reading any code other than its externally visible declarations. and to achieve this by supplementing the declarations with comments
- 
- [[POSD - how to write better comments - pick conventions]]
- [[POSD - how to write better comments - don't repeat the code]]


comments augment the code by providing information at a different level of detail some comments provide information at a lower more detailed level than the code; these comments add precision by clarifying the exact meaning of the code. other comments provide information at a higher more abstract level than the code these comments offer intuition, such as the reasoning behind the code, or a simpler and more abstract way of thinking about the code. **Comments at the same level as the code are likely to repeat the code.**

[[POSD - low-level comments]]
[[POSD - higher-level comments]]
[[POSD - interface comments]]
[[POSD - implementation comments]]


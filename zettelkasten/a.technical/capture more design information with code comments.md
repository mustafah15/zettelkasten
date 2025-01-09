---
tags:
  - software-design
parent: "[[why to write code comments]]"
type: literature
---

## capture more design information with code comments

a reason for writing comments is that statements in a programming language can't capture all of the important information that was in the mind of the developer when the code was written. comments should record this information so that developers who come along later can easily understand and modify the code.
	- the guiding principle for comments is that **comments should describe things that aren't obvious from the code**
	- Sometimes low-level details aren't obvious. for example, when a pair of indices describes a range, it isn't obvious whether the elements given by the indices are inside the range or out.
	- Sometimes it's not clear why code is needed, or why it was implemented in a particular way.
	- Sometimes there are rules the developer followed, such as always invoking `a` before `b` you might be able to guess a rule by looking at all of the code, but this is painful and error-prone a comment can make the rule explicit and clear.


---
tags:
  - software-design
  - book
parent: "[[philosophy of software design]]"
type: literature
---

One of the most common decisions that you will face when designing a new module is whether to implement it as a [[general purpose module]] or [[special purpose module]]

A [[general purpose module]] you implement a module that can be used to address a broad range of problems, not just the ones that are important today, however, the [[general purpose module]] seems consistent with the investment mindset we discussed in [[strategic vs tactical programming]] where you spend a bit more time upfront to save time later on. **On the other hand, it's hard to predict the future needs of a software system so a general-purpose solution might include facilities that are never actually needed. Furthermore, if you implement something that is a too general purpose, it might not do a good job of solving the particular problem you have today, as result it's better to focus on today's needs, building just what you know you need and specializing it for the any you plan to use it today**.

If we take the special purpose approach and discover the additional uses later, we can always extend it to make it general purpose, also the [[special purpose module]] seems to be consistent with an incremental approach to software development

The sweet spot is to implement new modules in a somewhat general-purpose fashion. the phrase somewhat general purpose means that module functionality should reflect your current needs but its interface should not, instead the interface should be general enough to support multiple uses. the interface should be easy for today's needs without being tied specifically to them.

deeper:

- [[general purpose module]]
- [[special purpose module]]
- [[questions to find the right balance between general and special purpose approach]]
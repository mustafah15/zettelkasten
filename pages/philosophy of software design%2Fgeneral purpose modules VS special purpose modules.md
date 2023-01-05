---
title: philosophy of software design/general purpose modules VS special purpose modules
---

- one of most common decisions that you will face when designing a new module is whether to implement it as a [[general purpose module]] or [[special purpose module]]
- a [[general purpose module]] which you implement a module that can be used to address a broad range of problems, not just the ones that important today, however the [[general purpose module]] seems consistent with investment mindset we discussed in [[philosophy of software design/strategic vs tactical programming]] where you spend a bit more time upfront to save time later on. **on the other hand it's hard to predict the future needs of a software system so a general purpose solution might include facilities that are never actually needed. Furthermore if you implement something that is too general purpose, it might not do a good job of solving the particular problem you have today, as result it's better to focus on today's needs, building just what you know you need and specialising it for the ay you plan to use it today**.
- if we take the special purpose approach and discover the additional uses later, you can always extend it to make it general purpose, also the [[special purpose module]] seems to be consistent with an incremental approach to software development
- the sweet spot is to implement new modules in a somewhat general purpose fashion. the phrase somewhat general purpose means that module functionality should reflect your current needs but it's interface should not, instead the interface should be general enough to support multiple uses. the interface should be easy for to today's needs without being tied specifically to them.
- [[questions to help you find the right balance between general purpose approach and special purpose approach]]
-
- [[why starting with general purpose design is not the best idea]]
-
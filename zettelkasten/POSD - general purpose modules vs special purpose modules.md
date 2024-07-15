---
tags:
  - software-design
  - book
parent: "[[philosophy of software design]]"
type: reference
---
- [[general purpose module]]
- [[special purpose module]]


One of the most common decisions that you will face when designing a new module is whether to implement it as a [[general purpose module]] or [[special purpose module]]

A [[general purpose module]] you implement a module that can be used to address a broad range of problems, not just the ones that are important today, however, the [[general purpose module]] seems consistent with the investment mindset we discussed in [[POSD - strategic vs tactical programming]] where you spend a bit more time upfront to save time later on. **On the other hand, it's hard to predict the future needs of a software system so a general-purpose solution might include facilities that are never actually needed. Furthermore, if you implement something that is a too general purpose, it might not do a good job of solving the particular problem you have today, as result it's better to focus on today's needs, building just what you know you need and specializing it for the any you plan to use it today**.

If we take the special purpose approach and discover the additional uses later, we can always extend it to make it general purpose, also the [[special purpose module]] seems to be consistent with an incremental approach to software development

The sweet spot is to implement new modules in a somewhat general-purpose fashion. the phrase somewhat general purpose means that module functionality should reflect your current needs but its interface should not, instead the interface should be general enough to support multiple uses. the interface should be easy for today's needs without being tied specifically to them.

## Questions to help you find the right balance between [[general purpose approach]] and [[special purpose approach]]

- **What is the simplest interface that will cover all my current needs**? 
	- if you reduce the number of methods in an API without reducing the overall capabilities, then you are probably creating a more general-purpose method. Reducing the number of methods makes sense only as long as the API for each individual method stays simple; if you have to introduce lots of additional arguments in order to reduce the number of methods, then you may not really be simplifying things
- In how many situations will this method be used?
	- if a method is designed for one particular use it is a red flag that it may be too special purpose. see if you can replace several special methods with a single general-purpose method
- Is this API easy to use for my current needs?
	- This question can help you to determine when you have gone too far in making an API simple and general-purpose. If you have to write a lot of additional code to use a class for your current purpose, that's a red flag that the interface doesn't provide the right functionality
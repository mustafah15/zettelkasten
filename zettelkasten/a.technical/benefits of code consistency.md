---
tags:
  - book-notes
  - software-design
parent: "[[philosophy of software design]]"
aliases:
  - code consistency
type: literature
---
- consistency is a powerful tool for reducing the complexity of a system and making its behavior more obvious. If a system is consistent it means that similar things are done in similar ways, and dissimilar things are done in different ways, Consistency creates cognitive leverage: once you have learned how something is done in one place you can use that knowledge to immediately understand other places that use the same approach. If a system is not implemented in a consistent fashion developers must learn about each situation separately. this will take more time.
- consistency also reduces mistakes if a system is not consistent two situations may appear the same when in fact they are different. A developer may see a pattern that looks familiar and make incorrect assumptions based on previous encounters with that pattern on the other hand if the system is consistent assumptions made based on familiar-looking situations will be safe consistency allows developers to work more quickly with fewer mistakes.

- [[examples of code consistency]]
- [[how to ensure code consistency]]
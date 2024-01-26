---
tags:
  - book-notes
  - software-design
related: "[[philosophy of software design]]"
type:
  - literature
aliases:
  - code consistency
---
- consistency is a powerful tool for reducing the complexity of a system and making its behavior more obvious. If a system is consistent it means that similar things are done in similar ways, and dissimilar things are done in different ways, Consistency creates cognitive leverage: once you have learned how something is done in one place you can use that knowledge to immediately understand other places that use the same approach. If a system is not implemented in a consistent fashion developers must learn about each situation separately. this will take more time.
- consistency also reduces mistakes if a system is not consistent two situations may appear the same when in fact they are different. A developer may see a pattern that looks familiar and make incorrect assumptions based on previous encounters with that pattern on the other hand if the system is consistent assumptions made based on familiar-looking situations will be safe consistency allows developers to work more quickly with fewer mistakes.
### examples of consistency
- names [[POSD - names should be consistent|names should be consistent]]
- coding styles. it's common nowadays for development organizations to have style guides that restrict program structure beyond the rules enforced by compilers.
- Interfaces: An interface with multiple implementations is another example of consistency once you understand one implementation of the interface any other implementation becomes easier to understand because you already know the features it will have to provide.
- Design patterns: Design patterns are generally accepted solutions to certain common problems such as the model view controller approach to user interface design. if you can use an existing design pattern to solve the problem the implementation will proceed more quickly it is more likely to work and your code will be more obvious to readers.
- Invariants. An Invariant is a property of a variable or structure that is always true for example, a data structure storing limes of text might enforce an invariant that each line is terminated by a new line character. Invariants reduce the number of special cases that must be considered in code and make it easier to reason about the code's behavior.
### ensuring consistency
- consistency is hard to maintain especially when many people work on a project over a long time. people in one group may not know about conventions established in another group, and newcomers don't know the rules so they unintentionally violate the conventions and create new conventions that conflict with existing ones, so here are a few tips to establish and maintain consistency
- **Document**: create a document that lists the most important overall conventions such as coding style guidelines and place that document in a spot where developers are likely to see it
- **Enforce:** Even with good documentation it's hard for developers to remember all of the conventions, the best way to enforce conventions is to write a tool that checks for violations and makes sure that code cannot be committed to the repository unless it passes the checker.
- **When in Rome..** The most Important Convention of all is that every developer should follow the old adage "When In Rome, Do as the Romans do" When working on a new project look around to see how the existing code is structured. when you see anything that looks like it might possibly be a convention follow it. Don't change existing conventions Resist the urge to "improve" on existing conventions. Having a "better idea" is not a sufficient excuse to introduce inconsistencies.
---
tags:
  - system-design
type: literature
parent: "[[benefits of code consistency|code consistency]]"
---

- consistency is hard to maintain especially when many people work on a project over a long time. people in one group may not know about conventions established in another group, and newcomers don't know the rules so they unintentionally violate the conventions and create new conventions that conflict with existing ones, so here are a few tips to establish and maintain consistency
- **Document**: create a document that lists the most important overall conventions such as coding style guidelines and place that document in a spot where developers are likely to see it
- **Enforce:** Even with good documentation it's hard for developers to remember all of the conventions, the best way to enforce conventions is to write a tool that checks for violations and makes sure that code cannot be committed to the repository unless it passes the checker.
- **When in Rome..** The most Important Convention of all is that every developer should follow the old adage "When In Rome, Do as the Romans do" When working on a new project look around to see how the existing code is structured. when you see anything that looks like it might possibly be a convention follow it. Don't change existing conventions Resist the urge to "improve" on existing conventions. Having a "better idea" is not a sufficient excuse to introduce inconsistencies.
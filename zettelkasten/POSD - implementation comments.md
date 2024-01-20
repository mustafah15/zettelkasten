---
tags:
  - book-notes
  - software-design
related: "[[POSD - how to write better comments]]"
type:
  - literature
---
- implementation comments are the comments that appear inside methods to help readers understand how they work internally. Most methods are so short and simple that they don't need any implementation comments given the code and the interface comment, it's easy to figure out how a method works.
- The main goal of implementation comments is to help readers understand what the code is doing not how it does it. once readers know what the code is trying to do, it's usually easy to understand how the code works. for short methods, the code only does one thing which should be already described in its interface comment, so no implementation comments are needed. longer methods have several blocks of code that do different things as part of the method's overall task. add a comment before each of the major blocks to provide a high-level description of what that block does.
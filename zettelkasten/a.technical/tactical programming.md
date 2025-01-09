---
tags:
  - software-design
parent: "[[strategic vs tactical programming]]"
deeper: "[[tactical tornado]]"
against: "[[strategic programming|strategic programming]]"
related: "[[philosophy of software design]]"
type: literature
---
Many programmers approach software development with a mindset that the author calls **tactical programming**. This approach focuses on quickly getting something to work, such as implementing a new feature or fixing a bug. At first glance, this seems reasonable—what could be more important than writing functional code?

However, tactical programming makes it nearly impossible to achieve good system design because it is fundamentally short-sighted. When programming tactically, the goal is to complete tasks as quickly as possible, leaving little room for planning.

To speed things up, you might introduce minor inefficiencies or "quick fixes," thinking they’re harmless. But complexity in software design is incremental—it grows from the accumulation of small compromises. If each programming task adds a bit of complexity, the system will gradually become more difficult to manage.

Eventually, these complexities cause problems, and you’ll regret the shortcuts you took. Yet, the pressure to deliver new features often overrides the desire to refactor and clean up existing code. Refactoring slows down immediate progress, so instead, you apply quick patches to work around the issues. These patches, however, only add more complexity.

Before long, the codebase becomes a tangled mess. By that point, cleaning it up would require months of effort.

almost every software development organisation has at least one developer who takes tactical programming to the extreme: **a [[tactical tornado]]** hopefully, I am not one of them.


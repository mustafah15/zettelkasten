---
tags:
  - software-design
  - book-notes
parent: "[[POSD - strategic vs tactical programming]]"
aliases:
  - tactical programming
type: reference
---
most programmers approach software development with a mindset I call tactical programming in this approach your main focus is to get something working such as a new feature or a bug fix. at first glance, this seems totally reasonable what could be more important than writing code that works?

tactical programming makes it nearly impossible to produce a good system design as the problem with tactical programming is that it is shortly sighted, if you are programming tactically you are trying to finish a task as quickly as possible as a result planning for the future is not a priority you don't spend much time looking for the best design; you just want to get something working soon. you tell yourself that it's okay to add a bit of [[POSD - complexity in software design]] or introduce a small kludge or two, that allows the current task to be completed more quickly, this is how systems become complicated as we discussed complexity is incremental the accumulations of dozens or hundreds of small things if you programming tactically each programming task will contribute a few of these complexities each of them probably seems like a reasonable compromise in order to finish the current task quickly. before long some of the complexities will start causing problems, and you will begin to wish that you didn't take those shortcuts but you will tell yourself that it's more important to get the next feature working than to go back and refactor existing code. refactoring will definitely slow down the current task so you look for quick patches to work around any problems you encounter this just creates more complexity. pretty soon the code is a mess, but by this point, things are so bad that it would take months of work to clean up.

almost every software development organization has at least one developer who takes tactical programming to the extreme: **a [[tactical tornado]]**.

![[tactical tornado]]
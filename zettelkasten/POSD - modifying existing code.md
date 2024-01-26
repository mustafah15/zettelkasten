---
tags:
  - book-notes
  - software-design
related: "[[philosophy of software design]]"
type:
  - literature
aliases:
  - modifying existing code
---
we discussed the difference between [[POSD - tactical programming]] and [[POSD - strategic programming]]

in [[POSD - tactical programming]] the primary goal is to get something working quickly even if that results in additional complexity; in [[POSD - strategic programming]] the most important goal is to produce great system design.

if you want to have a system that is easy to maintain and enhance then "working" isn't a high enough standard you have to prioritize design and think strategically. the idea also applies when you are modifying existing code.

when developers go into existing code to make changes such as bug fixes or new features they don't usually think strategically, a typical mindset is " what is the smallest possible change I can make that does what I need?" Sometimes developers justify this because they are not comfortable with the code being modified they worry that larger changes carry a greater risk of introducing new bugs. However, this also results in [[POSD - tactical programming]]. Each one of these minimal changes introduces a few special cases, dependencies, or other forms of complexity, As a result, the system design gets just worse and the problem accumulates with each step in the system's evolution.

if you want to maintain a clean design for a system you must take a strategic approach when modifying existing code.
- ideally, when you have finished with each change the system will have the structure it would have had if you designed it from the start with that change in mind, to achieve this goal you must resist the temptation to make a quick fix. instead, think about whether the current system design is still the best one in light of the desired change if not, reflector the system so that you end up with the best possible design. with this approach, the system design improves with every modification.

Whenever you modify any code try to find a way to improve the system design at least a little bit in the process. **If you are not making the design better you are probably making it worse.**

An investment mindset sometimes conflicts with the realities of commercial software development. if refactoring the system "the right way" would take the quick and dirty approach, particularly if you are working against a tight deadline, or if refactoring the system would create incompaptilites that affect many other people and teams, then the refactoring may not be practical.
### keep the comments near the code
- when you change existing code there's a good chance that the change with invalidate some of the existing comments. it's easy to forget to update comments when you modify code, which results in no longer accurate comments. inaccurate comments are frustrating to the reader begin to distrust all of the comments. fortunately, with a little disipline and a couple of guiding rules it's possiple to keep comments up-to-date without a huge effort.
- the best way to ensure that comments get updated is to position them close to the code they describe, so developers will see them when they change the code. the farther a comment is from its associated code, the less likely it is that it will be updated properly.
- when writing implementation comments don't put all the comments for an entire method at the top of the method, spread them out, pushing each comment down to the narrowest scope that includes all of the code referred to by the comment for example if a method has three major phases don't write one comment at the top of the method describes all of the phases in detail instead write a separate comment for each phase and position that comment just above the first line of code in that phase.
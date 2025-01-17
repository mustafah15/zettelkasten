---
tags:
  - book-notes
  - software-design
parent: "[[philosophy of software design]]"
aliases:
  - modifying existing code
type: literature
---
we discussed the difference between [[tactical programming]] and [[strategic programming]]

in [[tactical programming]] the primary goal is to get something working quickly even if that results in additional complexity; in [[strategic programming]] the most important goal is to produce great system design.

if you want to have a system that is easy to maintain and enhance then "working" isn't a high enough standard you have to prioritize design and think strategically. the idea also applies when you are modifying existing code.

when developers go into existing code to make changes such as bug fixes or new features they don't usually think strategically, a typical mindset is " what is the smallest possible change I can make that does what I need?" Sometimes developers justify this because they are not comfortable with the code being modified they worry that larger changes carry a greater risk of introducing new bugs. However, this also results in [[tactical programming]]. Each one of these minimal changes introduces a few special cases, dependencies, or other forms of complexity, As a result, the system design gets just worse and the problem accumulates with each step in the system's evolution.

if you want to maintain a clean design for a system you must take a strategic approach when modifying existing code.
- ideally, when you have finished with each change the system will have the structure it would have had if you designed it from the start with that change in mind, to achieve this goal you must resist the temptation to make a quick fix. instead, think about whether the current system design is still the best one in light of the desired change if not, reflector the system so that you end up with the best possible design. with this approach, the system design improves with every modification.

Whenever you modify any code try to find a way to improve the system design at least a little bit in the process. **If you are not making the design better you are probably making it worse.**

An investment mindset sometimes conflicts with the realities of commercial software development. if refactoring the system "the right way" would take the quick and dirty approach, particularly if you are working against a tight deadline, or if refactoring the system would create incompaptilites that affect many other people and teams, then the refactoring may not be practical.
[[keep the code comments near the code]]
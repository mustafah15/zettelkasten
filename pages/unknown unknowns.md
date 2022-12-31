---
title: unknown unknowns
---

- the third symptom of complexity is that it is not obvious which pieces of code should be modified to complete a task, or what information a developer must have to carry out the task successfully. of the three manifestations of complexity, unknown unknowns are the worst. an unknown unknowns means that there is something you need to know but there's no way for you to find out what it is, or even whether there is an issue or not. you won't find out about it until bugs appear after you make a change. 

- changes amplification is annoying but as long it is clear which code needs to be modified. the system will work once the change has been completed. similarly, a high cognitive load will increase the cost of a change but if it is clear which information to read, the change is sitll likely to be correct. with unknown unknowns it's unclear what to do or wether a proposed system which is impossible for system for any size. even this may not be suffcient, because a change may depend on a subtle design decision that was never documented. 

- One of the most important goals of a good design is for a system to be obvious. this is the opposite of high cognitive load and unknown unknowns. in obvious system a developer can quickly understand how existing code works and what is required to about what to do.

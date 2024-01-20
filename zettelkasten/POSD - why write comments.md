---
tags:
  - book-notes
  - software-design
related: "[[philosophy of software design]]"
type:
  - literature
---
- in-code documentation plays a crucial role in software design. Comments are essential to help developers understand a system and work efficiently, but the role of comments goes beyond this. Documentation also plays an important role in abstraction without comments you can't hide complexity. Finally, the process of writing comments, if done correctly will actually improve a system's design Conversely, a good software design loses much of its value if it is poorly documented.
- Many developers think that comments are a waste of time others see the value in comments but somehow never get around to writing them, However even in teams that encourage documentation, comments are often viewed as drudge work and many developers don't understand how to write them, so the resulting documentation is often mediocre.
- Inadequate documentation creates a huge and unnecessary drag on software development.
- There are three things that you should be convinced of about comments
	- good comments can make a big difference in the overall quality of software
	- it's not hard to write good comments
	- writing comments can be actually fun
- there are three justifications that developers usually use as to why they don't write comments

[[POSD - the myth of good code is self-documented]]
[[POSD - i don't have time to write comments]]
[[POSD - comments get out of date]]
[[POSD - comments might be worthless]]
## benefits of well-written comments
- the overall idea behind comments is to capture information that was in the mind of the designer but couldn't be represented in the code. this information ranges from low-level details, such as hardware quirk that motivates a particularly tricky piece of code, to high-level concepts such as the rationale for a class. when other developers come along later to make modifications the comments will allow them to work more quickly and accurately,
- without documentation future, developers will have to rederive guess at the developer's original knowledge this will take additional time and there is a risk of bugs if the new developer misunderstands the original designer's intentions
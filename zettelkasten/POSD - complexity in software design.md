---
tags:
  - software-design
  - book-notes
type:
  - literature
related: "[[philosophy of software design]]"
---
## complexity in software design 

It's all about complexity 

**but what is complexity**? complexity is anything related to the structure of a software system that makes it hard to understand and modify the system


Complexity can take many forms for example it might be hard to understand how a new piece of code works, and it might take a lot of effort to implement a small improvement, you also can think of complexity in terms of cost and benefit. complex systems it takes a lot of work to implement even small improvements. in a simple system, larger improvements can be implemented with less effort.

the overall complexity of a system is determined by the complexity of each part (p) weighted by the fraction of time developers spend working on that part.
- c = cp
complexity is more apparent to readers than writers. if you write a piece of code and it seems simple to you, other people think it's complex. then it's complex when you find yourself in a situation like this, it's worth probing the other developers to find out why the code seems complex to them; there are probably some interesting lessons to learn from the disconnect between your opinion and theirs.your job as a developer is not just to create code that you can work with easily but also to create code that others can work with easily.

complexity is incremental 

complexity isn't caused by a single catastrophic error it accumulates in lots of small chunks a single dependency or obscurity by itself is unlikely to affect significantly the maintainability of a software system. complexity comes because hundreds or thousands of small dependencies and obscurities build up over time. eventually, there are so many of these small issues that every possible change to the system is affected by several of them.
the incremental nature of complexity makes it hard to control it's easy to convince yourself that a little bit of complexity introduced by your current change is not a big deal however if every developer takes this approach for every change complexity accumulates rapidly.
once complexity has accumulated it is hard to eliminate since fixing a single dependency or obscurity will not by itself make a big difference in order to slow the growth of complexity you must adopt a zero-tolerance philosophy to eliminate it.


[[fighting against complexity]]
[[symptoms of complexity]]
[[causes of complexity]]


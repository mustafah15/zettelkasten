---
tags:
  - book-notes
  - software-design
related: "[[POSD - complexity in software design]]"
type:
  - fleeting
aliases:
  - complexity is incremental
---
complexity is incremental 

complexity isn't caused by a single catastrophic error it accumulates in lots of small chunks a single dependency or obscurity by itself is unlikely to affect significantly the maintainability of a software system. complexity comes because hundreds or thousands of small dependencies and obscurities build up over time. eventually, there are so many of these small issues that every possible change to the system is affected by several of them.
the incremental nature of complexity makes it hard to control it's easy to convince yourself that a little bit of complexity introduced by your current change is not a big deal however if every developer takes this approach for every change complexity accumulates rapidly.
once complexity has accumulated it is hard to eliminate since fixing a single dependency or obscurity will not by itself make a big difference in order to slow the growth of complexity you must adopt a zero-tolerance philosophy to eliminate it.
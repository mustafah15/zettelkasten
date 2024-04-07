---
tags:
  - book-notes
  - software-design
type:
  - literature
related: "[[POSD - better together or better apart]]"
---
The issue of when to [[POSD - Module Division and Complexity]] applies not just to classes, but also to methods: are there times when it is better to divide an existing method into multiple smaller methods? or, should two smaller methods be combined into one larger one?

long methods tend to be more difficult to understand than shorter ones so many people argue that length alone is a good justification for breaking up a method, Students in classes are then given rigid criteria such as "split up any methods longer than 20 lines!"

However length by itself is rarely a good reason for splitting up a method, in general, developers tend to break up methods too much splitting up a method introduces an additional interface which makes the code harder to read if the pieces are actually related, you shouldn't break up a method unless it makes the overall system simpler;
Long methods aren't always bad for example,
- suppose a method contains five 20-line blocks of code that are executed in order. if the blocks are relatively independent then the method can be read and understood one block at a time; there's not much benefit in moving each of the blocks into a separate method.
- if the blocks have complex interactions, it's even more important to keep them together so readers can see all of the code at once; if each block is in a separate method readers will have to flip back and forth between these spread-out methods too understand the how they work together.
- Methods containing hundreds of lines of code are fine if they have a simple signature and are easy to read. These methods are [[deep modules]] (lots of functionality and simple interface) which is good.

When designing methods the most important goal is to provide clean and simple abstractions. **Each method should do one thing and do it completely**. The method should have a clean and simple interface so that users don't need to have much information in their heads to use it correctly. the method should be deep; its interface should be much simpler than its implementation. if a method has all of these properties then it probably does not matter whether it is long or not.
Splitting up a method only makes sense if it results in cleaner abstractions overall.
![[conjoined methods]]

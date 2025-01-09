---
tags:
  - book-notes
  - software-design
parent: "[[philosophy of software design]]"
type: literature
---
[[obscurity|obscurity]] is one of the two main causes of complexity which occurs when important information about the system is not obvious to a new developer the solution to the obscurity problem is to write code in a way that makes it obvious.

If the code is obvious it means that someone can read the code quickly without much thought and their first guesses about the behavior or meaning of the code will be correct if the code is obvious a reader doesn't need to spend much time or effort to gather all information they need to work with the code.

If the code is not obvious then a reader must expend a lot of time and energy to understand it not only does this reduce their efficiency but it also increases the likelihood of misunderstanding and bugs obvious code needs fewer comments than nonobvious code.

Obvious is in the mind of the reader: it's easier to notice that someone else's code is nonobvious than to see problems with your own code. thus the best way to determine the obvious of code is through code reviews if someone reading your code says it's not obvious, then it's not obvious no matter how clear it may seem to you by trying to understand what made the code nonobovious you will learn how to write better code in the future.

deeper:

- [[things that can make the code more obvious]]
- [[things that make the code less obvious]]
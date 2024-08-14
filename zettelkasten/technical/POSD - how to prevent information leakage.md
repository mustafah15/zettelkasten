---
tags:
  - book-notes
  - software-design
parent: "[[POSD - information leakage|information leakage]]"
type: reference
---
## How to prevent information leakage?
- if you think you have information leakage in your design ask yourself
- How Can I reorganize these classes so that this particular piece of knowledge only affects a single class?
- if the affected classes are relatively small and closely tied to the leaked information, it may make sense to merge them into a single class
- another possible approach is to pull the information out of all of the affected classes and create a new class that encapsulates just that information. however, this approach will be effective only if you find a simple interface that abstracts away from the details of the new class exposes most of the knowledge through its interface then it won't provide much value as you simply replaced back-door leakage with leakage through an interface

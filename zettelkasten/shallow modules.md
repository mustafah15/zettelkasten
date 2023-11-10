---
tags:
  - software-design
related: "[[POSD - modules should be deep]]"
---
a shallow module is one with a relatively complex interface, but not much functionality it does not hide much complexity.

for example, a class that implements linked lists is shallow. it doesn't take much code to manipulate linked lists so the linked list abstraction doesn't hide very many details the complexity of a linked list interface is nearly as great as the complexity of its implementation. shallow classes are sometimes unavoidable, but they don't provide help much in managing complexity.

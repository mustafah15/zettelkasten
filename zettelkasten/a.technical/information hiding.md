---
tags:
  - system-design
aliases:
  - information hiding
parent: "[[information hiding and information leakage]]"
type: literature
deeper: "[[how information hiding reduces complexity]]"
against: "[[information leakage|information leakage]]"
---
## Information Hiding 

the most important technique for achieving deep modules is information hiding. the basic idea is that each module should encapsulate a few pieces of knowledge, which represent design decisions. the knowledge is embedded in the implementation of the modules but does not appear in its interface so it is not visible to other modules the information hidden with the module usually consists of details about how to implement some mechanism, for example
- how to store information in a btree
- how to implement the TCP network protocol
- how to parse JSON document
the hidden information includes data structures and algorithms related to the mechanism it can also include lower level details such as the size of a page, and it can include higher-level concepts that are more abstract such as an assumption that most files are small.


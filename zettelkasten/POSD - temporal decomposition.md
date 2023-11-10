---
tags:
  - system-design
type:
  - literature
aliases:
  - temporal decomposition
related: "[[POSD - information hiding and information leakage]]"
---
One common cause of [[POSD - information leakage|information leakage]] is a design style called temporal decomposition. In this style designing a system corresponds to the time order in which operations will occur. Consider an application that reads a file in a particular format modifies the content of the file and then writes the file out again. With Temporal Decomposition, this application might be broken into three classes one to read the file, one to perform the modifications, and a third one to write out the new version. both the reading and writing file steps have knowledge about the file format which results in [[POSD - information leakage|information leakage]] the solution is to combine the core mechanisms of reading and writing files into a single class this class will be used during both the reading and writing phases of the application

it's easy to fall into the trap of temporal decomposition because the order in which operations must occur is often on your mind when you code however, most design decisions manifest themselves at several different times over the life of the application as a result temporal decomposition often results in information leakage.

when designing modules, focus on the knowledge that is needed to perform each task not the order in which tasks occur.

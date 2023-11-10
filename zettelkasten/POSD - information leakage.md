---
tags:
  - software-design
type:
  - literature
related: "[[POSD - information hiding and information leakage]]"
aliases:
  - information leakage
---
the opposite of [[POSD - information hiding|information hiding]] is information leakage. 
**information leakage occurs when a design decision is reflected in multiple modules.** when this happens it creates a dependency between the modules as any change to that design decision will require changes to all of the involved modules. 
if a piece of information is reflected in the interface for a module then by definition it has been leaked that is why simpler interfaces tend to correlate with better information hiding. *HOWEVER*, information can be leaked even if it doesn't appear in a module interface. for example, suppose two classes both have knowledge of a particular file format even if neither class exposes that information in its interface, they both depend on the file format if the format changes, both classes will need to be modified. back door leakage like this is more pernicious than leakage through an interface because it isn't obvious.
information leakage is one of the most important red flags in software design. one of the best skills you can learn as a software designer is a high level of sensitivity to information leakage.

## How to prevent information leakage?
- if you think you have information leakage in your design ask yourself
- How Can I reorganize these classes so that this particular piece of knowledge only affects a single class?
- if the affected classes are relatively small and closely tied to the leaked information, it may make sense to merge them into a single class
- another possible approach is to pull the information out of all of the affected classes and create a new class that encapsulates just that information. however, this approach will be effective only if you find a simple interface that abstracts away from the details of the new class exposes most of the knowledge through its interface then it won't provide much value as you simply replaced back-door leakage with leakage through an interface


## leakage types
- **interface leakage**: a piece of information is reflected in the interface for a module then by definition, it has been leaked
- **back door leakage**: for example, suppose two classes both have knowledge of a particular file format even if neither class exposes that information in its interface, they both depend on the file format if the format changes, both classes will need to be modified.

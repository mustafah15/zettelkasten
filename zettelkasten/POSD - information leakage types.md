---
tags:
  - book-notes
  - software-design
related: "[[POSD - information leakage|information leakage]]"
type:
  - literature
---
## information leakage types
- **interface leakage**: a piece of information is reflected in the interface for a module then by definition, it has been leaked
- **back door leakage**: for example, suppose two classes both have knowledge of a particular file format even if neither class exposes that information in its interface, they both depend on the file format if the format changes, both classes will need to be modified.

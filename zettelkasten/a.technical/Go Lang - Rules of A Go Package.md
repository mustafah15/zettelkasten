---
tags:
  - tools
  - goLang
type: permanent
---
- A package is a collection of files located in the same folder that all share the same package name. Each Go file starts with the package declaration.
- It is customary to name the package after the name of the directory.
- Avoid overly long names if possible. Prefer a lowercase single word. If you compress the word, avoid abbreviations that make the package name more ambiguous.
- Any symbol (functions, types, variables, constants) starting with a capital letter will be exported outside the package and can be used by other packages, while those starting with a lowercase will not.
- camelCase and PascalCase are the conventions for functions, variables, constants and types. Package names stay lowercase

---
tags:
  - book-notes
  - software-design
type:
  - literature
related: "[[POSD - better together or better apart]]"
---
### Bringing pieces of code together is most beneficial if they are closely related. if the pieces are unrelated, they are probably better off apart
Here are a few indications that the two pieces of code are related:
- they share information for example both pieces of code might depend on the syntax of a particular type of document.
- they are used together anyone using one of the pieces of code is likely to use the other as well. this form of relationship is only compelling if it is bidirectional.
- they overlap conceptually, in that there is a simple higher-level category that includes both of pieces of code. for example, searching for a substring and case conversion both fall under the category of string manipulation flow control, and reliable delivery both fall under the category of network communication.
- if it's hard to understand one of the pieces of code without looking at the other

## BRING TOGETHER IF:
- If information is shared
	- if there's shared information between two components is better to combine them into one the code will get shorter and simpler.
- if it will simplify the interface
	- when two or more modules are combined into a single module, it may be possible to define an interface for the new module that is simpler or easier to use than the original one, This often happens when the original modules each implement a part of the solution to a problem. In addition, when the functionality of two or classes is combined it may be possible to perform some functions automatically, so most users need not be aware of them.
- if it will eliminate duplication
	- if you find the same pattern of code repeated over and over, see if you can reorganize the code to eliminate the repetition. One approach is to factor the repeated code out into a separate method and replace the repeated code snippets with calls to the method.
	- This approach is most effective if the repeated code snippet is long and the replacement method has a simple signature. if the snippet is only one or two lines long there may not be much benefit in replacing it with a method call. if the snippet intersects in a complex way with its environment ( such as by accessing numerous local variables then the replacement methods might require a complex signature) which would reduce its value.
	- Another way to eliminate duplication is to refactor the code so that the snippet in question only needs to be executed in one place.
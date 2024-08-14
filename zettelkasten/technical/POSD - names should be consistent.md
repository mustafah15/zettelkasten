---
tags:
  - book-notes
  - software-design
parent: "[[POSD - choosing names]]"
aliases:
  - names should be consistent
type: reference
---
- the second important property of good names is consistency, in any program, there are certain variables that are used over and over again. for example, a file system manipulates block numbers repeatedly. foreach of these common usages, pick a name to use for that purpose and use the same name everywhere for example a file system might always use fileBlock to hold the index of a block within a file.
- consistent naming reduces the cognitive load in much the same way as reusing a common class once the reader has seen the name in one context they can reuse their knowledge and instantly make assumptions when they see the name in a different context.
- consistency has three requirements:
	- first, always use the common name for the given purpose;
	- second, never use the common name for other than the given purpose
	- third, make sure that the purpose is narrow enough that all variables with the name have the same behavior.

- sometimes you will need multiple variables that refer to the same general sort of thing. for example, a method that copies file data will need to block numbers one for the source and one for the destination. when this happens use the common name for each variable but add a distinguishing prefix, such as `srcFileBlock` and `dstFileBlock`.
- loops are another Area where consistent naming can help. if you use names such as i and j for loop variables, always use `i` in the outermost loop and `j` for nested loops. this allows readers to make safe assumptions about what's happening in the code when they see a given name.
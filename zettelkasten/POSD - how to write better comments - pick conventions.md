---
tags:
  - book-notes
  - software-design
parent: "[[POSD - how to write better comments]]"
type: reference
---
- the first step in writing comments is to decide on conventions for commenting, such as what you will comment on and the format you will use for comments. if you are programming in a language for which there exists a document compilation tool such as Javadoc for java the author recommends following the conventions of those tools. None of these conventions is perfect, but the tools provide enough benefits to make up for that. if you are programming where there are no existing conventions to follow, try to adopt the conventions from some other language or project that is similar, this will make it easier for other developers to understand and adhere to your conventions.
- conventions serve two purposes.
	- first, they ensure consistency, which makes comments easier to read and understand.
	- second, they help to ensure that you actually write comments if you don't have a clear idea of what you are going to comment on and how it's easy to end up writing no comments at all.

- most comments fall into one of the following categories:

- Interface
	- a comment block that immediately precedes the declaration of a module such as a class, data structure, function, or method. the comment describes the overall abstractions provided by a class or a function and describes its overall behavior, its arguments and return value if any side effects or exceptions that it generates, and any other requirements the caller must satisfy before invoking the method.

- Data-structure member
	- a comment next to the declaration of a field in a data structure such as an instance variable or static variable for a class.

- Implementation comment
	- comment inside the code of a method for functions which describes how the code works internally.

- Cross module comment
	- a comment describing that cross modules boundaries

- the most important comments are those in the first two categories, everything should have interface comments occasionally the declaration for a variable or method is so obvious that there is nothing useful to add in a comment, implementation comments are often unnecessary, cross-module comments are the rarest of all and they are problematic to write when they are needed they are quite important
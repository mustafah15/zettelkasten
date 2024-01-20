---
tags:
  - book-notes
  - software-design
related: "[[philosophy of software design]]"
type:
  - literature
---
- designing software is hard so it's unlikely that your first thoughts about how to structure a module or system will produce the best design. you will end up with a much better result if you consider multiple options for each major design decision.
- suppose you are designing a class that will manage the next file for a GUI text editor the first step is to define the interface that the class will present to the rest of the editor; rather than picking the first idea that comes to mind, consider several possibilities. One choice is a line-oriented interface, with operations to insert, modify, and delete a whole line of text. Another option is an interface based on individual character insertion and deletions. A third choice is a string-oriented interface that operates on arbitrary ranges of characters that may cross line boundaries. you don't need to pin down every feature of each alternative it's sufficient at this point to sketch out a few of the most important methods.
- Even if you are certain that there is only one reasonable approach consider a second design anyway no matter how bad you think it will be. It will be instructive to think about the weaknesses of that design and contrast them with the features of the other designs.
- After you have roughed out the designs for the alternatives, make a list of the pros and cons of each one. the most important consideration for an interface is the ease of use for higher-level software.
- it's also worth considering other factors like:
	- does one laternative have a simpler interface than another?
	- is one interface more general purpose than another?
	- does one interface enable a more efficient implementation than another?

- once you have compared alternative designs you will be in a better position to identify the best design. the best choice may be one of the alternatives or you may discover that you can combine features of multiple alternatives into a new design that is better than any of the original choices.
- design it twice principle can be applied at many levels in a system. for a module you can use this approach first to pick the interface, then you can apply it again when you are designing the implementation; the goals will be different for the implementation than for the interface as for the implementation the most important things are simplicity and performance, it's also useful to explore multiple designs at higher levels in the system into major modules. In each case, it's easier to identify the best approach if you can compare a few alternatives.
- this will not only improves your designs but also improve your design skills the process of devising and comparing multiple approaches will teach you about the factors that make designs better or worse over time this will make it easier for you to rule out bad designs and hone in on really great ones.
- lower level comments add precision
- precision is most useful when commenting variable declarations such as class instance variables, method arguments and return values. the name and type in a variable declaration are typically not very precise comments can fill in missing details such
	- what are the units for this variable?
	- are the boundary conditions inclusive or exclusive?
	- if a null value is permitted what does it imply?
	- if a variable refers to a resource that must eventually be freed or closed, who is responsible for freeing or closing it.
	- are these certain properties that are always true for the variable?
- some of this information could potentially be figured out by examining all of the code where the variable is used. however, this is time-consuming and error-prone; the declaration comment should be clear and complete enough to make this unneccessary.
- when we say that the comment  for a declaration should describe things that aren't obvious from the code "the code" refers to the code next to the comment
- the most common problem with the comments for variables is that the comments can be too vague
	- ```c
	  //current offset in resp buffer
	  unit32_t offset 
	  
	  //contain all line width inside the document and number of appearances.
	  private TreeMap<Integer, Integer> lineWidth;
	  ```
- in the first example it's not clear what "current" means.
- in the second example, it's not clear that the keys in the `TreeMap` are line width and values are occurrence counts also, are widths measured in pixels or characters? the revised comments below provide additional details:
	- ```c
	  //position in this buffer of the first object that hasn't been returned
	  unit32_t offset 
	  
	  //Holds satistics about line lengths of the form <length, count>
	  // where lenght is the number of characters in a line (including the new line)
	  //and count is the number of the lines with exactly that many characters 
	  // if there are no lines with a particular length, then there is no entry for that length
	  private TreeMap<Integer, Integer> numlinesWithLength;
	  ```
- the second declaration uses a longer name that conveys more information it also changes width to length because this term is more likely to make people think that the units are characters rather than pixels. notice that the second comment documents not only the details of each entry but also what it means if an entry is missing. when documenting a variable think nouns, not verbs in other words focus on what the variable represents not how it is manipulated
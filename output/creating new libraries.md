
  

Before creating a new library we need to take a few steps to make sure that we are not adding an extra complexity to the system overall or a new maintenance burden that we could avoid. 
remember when deciding whether to combine or separate, the goal is to reduce the complexity of the system as a whole and improve its modularity

Bringing pieces of code together can be most beneficial if they are closely related.
Here are a few signs that indicate that the two pieces of code are related:

- Information is shared
	- if there's shared information between two components is better to combine them into one the code will get shorter and simpler, for example, both pieces of code might depend on the syntax or business logic of a particular type of entity.
- Reduce interface complexity 
	- when two or more modules are kept into a single module, it may be possible to define an interface for the new module that is simpler or easier to use than the original one, This often happens when the original modules each implement a part of the solution to a problem. In addition, when the functionality of two or classes is combined it may be possible to perform some functions automatically, so most users need not be aware of them, for example, those modules are used together 

- They are used together anyone using one of the pieces of code is likely to use the other as well. this form of relationship is only compelling if it is bidirectional.
- If it's hard to understand one of the pieces of code without looking at the other.
so consider keeping the code together if: 

If the pieces are unrelated, they are probably better off apart
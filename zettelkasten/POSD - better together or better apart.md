---
tags:
  - book-notes
  - software-design
type:
  - literature
related: "[[philosophy of software design]]"
---
when deciding whether to combine or separate, the goal is to reduce the complexity of the system as a whole and improve its modularity.
The best way to to divide the system into a large number of small components, the smaller the components the simpler each individual component is likely to be however the act of subdividing creates additional complexity that was not present before subdivision:
- some complexity comes just from the number of components: the more components the harder to keep track of them all and the harder to find a desired component within the large collection. subdivision usually results in more interfaces. and every new interface adds complexity.
- subdivision can result in additional code to manage the components. for example, a piece of code that used a single object before subdivision might now have to manage multiple objects.
- subdivision creates separation: the subdivided components will be farther apart than they were before the subdivision. for example, methods that were together in the same class may be in different classes after subdivision and possibly in different files, separation makes it harder for developers to see the components at the same time, or even to be aware of their existence.
- subdivision can result in duplication: code that was present in a single instance before subdivision may need to be present in each of the subdivided components.

**But if the components are truly independent then separation is good**: it allows the developer to focus on a single component at a time without being distracted by the other components on the other hand if there are dependencies between components then separation is bad as developers will end up flipping back and forth between the components. even worse they may not be aware of the dependencies which can lead to bugs.

## separate general-purpose and special-purpose code
- if a module contains a mechanism that can be used for several different purposes, then it should provide just that one general-purpose mechanism. it should not include code that specializes the mechanism for a particular use, nor should it contain other general-purpose mechanisms special-purpose codes associated with a general-purpose should go normally in a different module.
- special-general-mix: when a general purpose mechanism also contains code specialized for a particular use of that mechanism this makes the mechanism more complicated and creates information leakage between the mechanism and the particular use case: future modifications to the use case are likely to require changes to the underlying mechanism as well.

## Bringing pieces of code together is most beneficial if they are closely related. if the pieces are unrelated, they are probably better off apart
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
## Splitting and Joining Methods

The issue of when to subdivide applies not just to classes, but also to methods: are there times when it is better to divide an existing method into multiple smaller methods? or, should two smaller methods be combined into one larger one?

long methods tend to be more difficult to understand than shorter ones so many people argue that length alone is a good justification for breaking up a method, Students in classes are then given rigid criteria such as "split up any methods longer than 20 lines!"

However length by itself is rarely a good reason for splitting up a method, in general, developers tend to break up methods too much splitting up a method introduces an additional interface which makes the code harder to read if the pieces are actually related, you shouldn't break up a method unless it makes the overall system simpler;
Long methods aren't always bad for example,
- suppose a method contains five 20-line blocks of code that are executed in order. if the blocks are relatively independent then the method can be read and understood one block at a time; there's not much benefit in moving each of the blocks into a separate method.
- if the blocks have complex interactions, it's even more important to keep them together so readers can see all of the code at once; if each block is in a separate method readers will have to flip back and forth between these spread-out methods too understand the how they work together.
- Methods containing hundreds of lines of code are fine if they have a simple signature and are easy to read. These methods are [[deep modules]] (lots of functionality and simple interface) which is good.

When designing methods the most important goal is to provide clean and simple abstractions. **Each method should do one thing and do it completely**. The method should have a clean and simple interface so that users don't need to have much information in their heads to use it correctly. the method should be deep; its interface should be much simpler than its implementation. if a method has all of these properties then it probably does not matter whether it is long or not.
Splitting up a method only makes sense if it results in cleaner abstractions overall.
![[conjoined methods]]

## Repetition
if the same piece of code (or code that is almost the same) appears over and over again that's a red flag that you haven't found the right abstractions.

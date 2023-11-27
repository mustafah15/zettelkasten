---
tags:
  - book-notes
related: "[[philosophy of software design]]"
type:
  - permanent
---
Many developers think that code comments are a waste of time and a code smell. they have many reasons for that. I was one of them until I read [a different opinion](https://www.amazon.de/Philosophy-Software-Design-John-Ousterhout/dp/1732102201/ref=asc_df_1732102201/?tag=&linkCode=df0&hvadid=310817730623&hvpos=&hvnetw=g&hvrand=8944799065997115965&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9115000&hvtargid=pla-516088603917&psc=1&th=1&ref=&adgrpid=70301320788) that convinced me to believe the opposite, so during this blog post, my present self will try to convince my past self with the following:  
- _Good comments can make a big difference in the overall quality of software.  
- It’s not hard to write good comments as writing comments can be fun._

Let’s get started with the reason why we should write comments. comments can be essential to improve engineers’ understanding of the system however the role of comments goes beyond this.  
comments can play an important role in abstraction as the idea of abstraction is to provide a simple way of thinking about something but is so detailed that it can be hard to see the abstraction from reading the code and a developer should be able to understand the abstraction provided by a module (function, class) without reading any code other than it’s externally visible declarations and you can achieve that by supplementing the code declarations with comments. as comments can provide a simpler higher-level view even if this information can be deduced by reading the code, as we don’t want to force users of a module to do that because reading the code is time-consuming and forces them to consider a lot of information that isn’t needed to use the module.

Now let’s talk about justifications my past self used to use in order not to write comments:

## Good Code Is Self-documenting

I used to think that comments were a waste of time because “clean code” should be self-documenting according to other books and developers’ communities like Laravel for example. Sure there are things that you can do when writing code to reduce the need for comments, such as choosing a good variable and function names, however, there is still a significant amount of design information that can’t be represented in code. as you can only specify formally in the code small part of a class’s interface, such as the signatures of its methods, However, the informal aspect of an interface such as:

- The high-level description of what each method does or the meaning of its result can only be described in comments
- There are many other examples of things that can’t be described in the code such as the reason for a particular design decision, or the conditions under which it makes sense to call a particular method.

Also, you can argue that if others want to know what a method does, they should just read the code of the method as this will be more accurate than any other comment. However, this would be time-consuming and painful, as you write code with the expectation that users will read method implementations, you will try to make each method as short as possible, so that it’s easy to read. if the method does anything nontrivial, you will break it up into several smaller methods. this will result in a large number of shallow methods and a shallow module which has a relatively complex interface, but not much functionality it does not hide much complexity. In order to understand the behavior of the top-level method, readers will probably need to understand the behavior of the nested methods. for large systems, it’s not practical for users to read the code to learn the behavior.

Comments allow us to capture the additional information that callers need thereby completing the simplified view while hiding implementation details that the user of the module might not be interested in.

## Comments can get out of date

Comments do sometimes get out of date, but this need not to be a major problem in practice keeping documentation up-to-date does not require an enormous effort. large changes to documentation are only required if there have been large changes to the code and the code changes will take more time than documentation changes, and the code review should provide a great mechanism for detecting and fixing comments.

## Comments might be worthless

of all the excuses, this is probably the one with the most valid every software developer has seen comments that provide no useful information, and most existing documentation is so-so at best, but this problem is solvable writing solid documentation/comments is not hard once you know how we will discuss this next.

# How To Write Better Comments

## Pick Convention

The first step in writing comments is to decide with your team on a conventions for commenting such as what you will comment on and the format you will use for comments, conventions serve two purposes first, they **ensure consistency** which makes comments easier to read and understand. second, they help to **ensure that you actually write comments**. If you don’t have a clear idea of what you are going to comment on and how it’s easy to end up writing no comments at all

## Don’t Repeat The Code

Unfortunately, many comments are not particularly helpful. the most common reason is that the comments repeat the code and to solve this problem it’s better after you write a comment the following question: could someone who has never seen the code write the comment just by looking at the code next to the comment? if the answer is yes then this comment does not make the code any easier to understand. another common mistake is to use the same words in the comment that appears in the name of the entity being documented. A first step towards writing good comments is to use different words in the comment from those in the name of the entity being described. Pick words for the comment that provide additional information about the meaning of the entity rather than just repeating its name.

## Write Comments First

One of the surest ways to produce poor-quality documentation is to write documentation at the end of the development process. writing the comments first makes documentation part of the design process, not only does this produce better documentation but it also produces better designs and it makes the process of writing documentation more enjoyable.

## A Different Way To Write Comments

A different approach to writing comments, is write the comments at the very beginning: for a new class start by writing the class interface comments next, write interface comments and signatures for the most important public methods but leave the method bodies empty. Iterate a bit over these comments until the basic structure feels about right. at this point write a declaration and comments for the most important class instance variables in the class. finally fill in the bodies of the methods, adding implementation comments as needed. while writing method bodies you might discover the need for additional methods and instance variables. for each new method write the interface comment before the body of the method; for instance, variables fill in the comment at the same time that I write the variable declaration. when the code is done the comments are also done there is never a backlog of unwritten comments.

This comments-first approach has three benefits.

- **Produces better comments:** If you write the comments as you are designing the class, the key design issues will be fresh in your mind, so it’s easy to record the. It’s better to write the interface comment for each method before its body so you can focus on the method abstraction and interface without being distracted by its implementation.
- **Improves the system design:** Comments can provide the only way to fully capture abstractions. and good abstraction is fundamental to good system design so if you write comments describing the abstractions at the beginning, you can review and tune the before writing the implementation code. To write a good comment you must identify the essence of a variable or piece of code what is the most important aspect of this thing? Is it important to do this early in the design process; otherwise you are just hacking the code. As comments can serve as a canary in the coal mine of complexity if a method or variable requires a long comment it is a red flag that you don’t have a good abstraction. also it is a good way to judge the complexity of an interface is from the comments that describe it. If the interface comment for a method provides all the information needed to use the method and is also short and simple, that indicates that the method has a simple interface.
- **Makes it more fun**: one of the most enjoyable parts of programming is the early design phase for a new class, where you flesh out the abstractions and structure for the class. most of your comments are written during this phase, and the comments are how you record and test the quality of your design decisions.

# Conclusion

Writing comments can be really useful to capture information that was in the mind of the developer but couldn’t be represented in the code without documentation future developers will have to guess the developer’s original knowledge which might lead to obscurity, comments can lead to better module abstraction, and to a better design overall if it’s well written.


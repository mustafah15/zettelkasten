alias:: posd
tags:: blog

- Many developers think that code comments are a waste of time. and they got so many reasons for that. I was one of them until a few weeks ago I read a different opinion that convinced me to believe the opposite, so during this blog post, my present self will try to convince my past self with the following:
	- Good comments can make a big difference in the overall quality of software.
	- It’s not hard to write good comments
	- Writing comments can be actually fun
-
- ### Here we go starting with the reason **why we should write comments.** 
  
  As comments are essential to help developers to understand a system and work efficiently however the role of comments goes beyond this as comments play important role in abstraction as the idea of abstraction is to provide a simple way of thinking about something but is so detailed that it can be hard to see the abstraction from reading the code and a developer should be able to understand the abstraction provided by a module (function, class) without reading any code other than it’s externally visible declarations and you can achieve that by supplementing the code declarations with comments. comments can provide a simpler higher-level view even if this information can be deduced by reading the code, we don’t want to force users of a module to do that because reading the code is time-consuming and forces them to consider a lot of information that isn’t needed to use the module.
  
  Now let’s talk about justifications my past self used to use in order not to write comments:
#### The myth of good code is self-documenting

I used to think that comments were a waste of time because “clean code” should be self-documenting according to many other books and developers' communities like Laravel for example. Sure there are things you can do when writing code to reduce the need for comments, such as choosing a good variable name, however, there is still a significant amount of design information that can’t be represented in code. as you can only specify formally in the code small part of a class’s interface, such as the signatures of its methods but the informal aspect of an interface, such as a high-level description of what each method does or the meaning of its result can only be described in comments, there are many other examples of things that can’t be described in the code such as the reason for a particular design decision, or the conditions under which it makes sense to call a particular method.

Also, you can argue that if others want to know what a method does, they should just read the code of the method: this will be more accurate than any other comment. it’s possible that a reader could deduce the abstract interface of the method by reading its code, but it would be time-consuming and painful as we mentioned before. in addition, if you write code with the expectation that users will read method implementations, you will try to make each method as short as possible, so that it’s easy to read. if the method does anything nontrivial, you will break it up into several smaller methods. this will result in a large number of shallow methods — a shallow module is one with a relatively complex interface, but not much functionality it does not hide much complexity — , in order to understand the behavior of the top-level method, readers will probably need to understand the behavior of the nested methods. for large systems, it isn’t practical for users to read the code to learn the behavior.

Comments allow us to capture the additional information that callers need thereby completing the simplified view while hiding implementation details that the user of the module might not be interested in.

examples from the laravel framework that has tons of comments actually that made code very pleasant to use 

#+BEGIN_EXPORT hiccup
[:figure {:name "2b72"} [:img {:src "https://cdn-images-1.medium.com/max/1600/1*APwuYUqE4RrvUdvg9m-s3Q.png"}] [:figcaption {} [:a {:href "https://github.com/laravel/framework/blob/10.x/src/Illuminate/Container/Container.php", :rel "noopener", :target "_blank"} "laravel’s container code"] " is an example of how laravel codebase is rich with good comments as documentation which might be the opposite of what a lot of people think"]]
#+END_EXPORT
#### comments can get out of date

comments do sometimes get out of date, but this need not to be a major problem in practice keeping documentation up-to-date does not require an enormous effort. large changes to documentation are only required if there have been large changes to the code and the code changes will take more time than documentation changes, and the code review should provide a great mechanism for detecting and fixing comments.
#### comments might be worthless 

of all excuses, this is probably the one with the most valid every software developer has seen comments that provide no useful information, and most existing documentation is so-so at best, but this problem is solvable writing solid documentation/comments is not hard once you know how we will discuss this later
-
### How To Write Better Comments
- #### Pick Convention
  collapsed:: true
	- the first step in writing comments is to decide on conventions for commenting such as what you will comment on and the format you will use for comments, conventions serve two purpose
		- first, they ensure consistency which makes comments easier to read and understand.
		- second, they help to ensure that you actually write comments if you don’t have a clear idea of what you are going to comment on and how it’s easy to end up writing no comments at all
	- Most comments fall into one of the following categories:
		- Interface: a comment block that immediately precedes the declaration of a module such as a class, data structure, function, or method. the comment describes the overall abstractions provided by a class or a function and describes its overall behavior, its arguments and return value if any side effects or exceptions that it generates, and any other requirements the caller must satisfy before invoking the method.
		- Data-structure member: a comment next to the declaration of a field in a data structure such as an instance variable or static variable for a class.
		- Implementation comment: comment inside the code of a method for functions which describes how the code works internally.
		- Cross module comment: a comment describing that cross modules boundaries.
- #### Don’t Repeat The Code
  collapsed:: true
	- unfortunately, many comments are not particularly helpful. the most common reason is that the comments repeat the code and to solve this problem it’s better after you write a comment the following question: could someone who has never seen the code write the comment just by looking at the code next to the comment? if the answer is yes then this comment does not make the code any easier to understand.
	- another common mistake is to use the same words in the comment that appears in the name of the entity being documented.
	- A first step towards writing good comments is to use different words in the comment from those in the name of the entity being described. Pick words for the comment that provide additional information about the meaning of the entity rather than just repeating its name
-
#### Write Comments First

One of the surest ways to produce poor-quality documentation is to write documentation at the end of the development process. writing the comments first makes documentation part of the design process, not only does this produce better documentation but it also produces better designs and it makes the process of writing documentation more enjoyable.

**A different way to write comments**

I used a different approach to writing comments, where I write the comments at the very beginning:
- for a new class start by writing the class [[philosophy of software design/how to write better comments/interface comments]]
- next, write interface comments and signatures for the most important public methods but leave the method bodies empty.
- Iterate a bit over these comments until the basic structure feels about right.
- at this point write a declaration and comments for the most important class instance variables in the class.
- finally fill in the bodies of the methods, adding implementation comments as needed.
- while writing method bodies you might discover the need for additional methods and instance variables. for each new method write the interface comment before the body of the method; for instance, variables fill in the comment at the same time that I write the variable declaration.
- when the code is done the comments are also done there is never a backlog of unwritten comments.
- #### the comments-first approach has three benefits.
	- first, it produces better comments if you write the comments as you are designing the class, the key design issues will be fresh in your mind, so it’s easy to record the. it’s better to write the interface comment for each method before its body so you can focus on the method abstraction and interface without being distracted by its implementation.
	- the second and most important benefit is that it improves the system design. comments provide the only way to fully capture abstractions. and good abstraction is fundamental to good system design so if you write comments describing the abstractions at the beginning, you can review and tune the before writing implementation code. to write a good comment you must identify the essence of a variable or piece of code what is the most important aspect of this thing? is it important to do this early in the design process; otherwise you are just hacking the code.
		- As comments can serve as a canary in the coal mine of complexity if a method or variable requires a long comment it is a red flag that you don’t have a good abstraction. as the best way to judge the complexity of an interface is from the comments that describe it. if the interface comment for a method provides all the information needed to use the method and is also short and simple, that indicates that the method has a simple interface.
		- Hard to describe, conversely, if there’s no way to describe a method completely without a long and complicated comment with the implementation to get a sense of how deep the method is; the interface comment must describe all the major features of the implementation. then the method is shallow as the comment describing a method or variable should be simple yet complete.
	- the third and final benefit of writing comments early is that it makes comment-writing more fun. one of the most enjoyable parts of programming is the early design phase for a new class, where you flesh out the abstractions and structure for the class. most of your comments are written during this phase, and the comments are how you record and test the quality of your design decisions.
- ### Conclusion  
  
  writing comments can be really useful to capture information that was in the mind of the designer but couldn’t be represented in the code without documentation future developers will have to guess the developer's original knowledge which might lead to obscurity, comments can lead to better module abstraction, and to a better design overall if it's well written.
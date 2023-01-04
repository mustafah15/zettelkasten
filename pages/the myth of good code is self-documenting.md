- some people believe that if code is written well, is it so obvious that no comments are needed this is a delicious myth, to be sure there are things you can do when writing code to reduce the need for comments, such as choosing a good variable name, however there still a significant amount of design information that can't be represented in code. for example, only a small part of a class's interface, such as the signatures of its methods  can be specified formally in the code the informal aspect of an interface, such as a high-level description of what each method does or the meaning of its result can only be described in comments, there are many other examples of things that can't be described in the code such as the rationale for a particular design decision, or the conditions  under which it makes sense to call a particular methods
- some developers argue that if others want to know what a method does, they should just read the code of the method: this will be more accurate than any other comment.  it's possible that a reader could deduce the abstract interface of the method by reading its code, but it would be time-consuming and painful. in addition, if you write code with the expectation that users will read method implementations, you will try to make each method as short as possible, so that it's easy to read. if the method does anything nontrivial, you will break it up into several smaller methods. this will result in a large number of shallow methods, furthermore, it does not really make the code easier to read
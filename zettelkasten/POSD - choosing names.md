---
tags:
  - book-notes
  - software-design
related: "[[philosophy of software design]]"
type:
  - literature
---
- selecting names for variables, methods, and other entities is one of the most underrated aspects of software design. good names are a form of documentation: they make code easier to understand. they reduce the need for other documentation and make it easier to detect errors. conversely, poor name choices increase the complexity of the code and create ambiguities and misunderstandings that can result in bugs.
- Name choices are an example of the principle that [[POSD - complexity is incremental|complexity is incremental]] choosing a mediocre name for a particular variable as opposed to the best possible name probably won't have much impact on the overall complexity of a system. however, software systems have thousands of variables choosing good names for all of these will have a significant impact on complexity and manageability.
- when choosing a name, the goal is to create an image in the mind of the reader about the nature of the things being named a good name conveys a lot of information about what the underlying entity is and is just as important when considering a particular name ask yourself the following **if someone sees this name in isolation, without seeing its declaration its documentation, or any code that uses the name how closely will they be able to guess what the name refers to? is there some other name that will paint a clearer picture** of course, there is a limit to how much information you can put in a single name; names become unwieldy if they contain more than two or three words, so the challenge is to find just a few words that capture the most important aspects of the entity.
- Names are a form of abstraction: they provide a simplified way of thinking about a more complex underlying entity. like other forms of abstraction, the best names are those that focus attention on what is most important about the underlying entity while omitting less important details.
- Good names have two properties Precision and Consistency
- [[POSD - names should be precise|names should be precise]]
- [[POSD - names should be consistent|names should be consistent]]

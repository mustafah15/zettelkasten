---
tags:
  - book-notes
  - ddd
related: "[[learning domain driven design]]"
type:
  - fleeting
aliases:
  - discovering domain knowledge
---
this chapter continues the topic of [[lddd -  analyzing business domains]] but in a different dimension: depth it focuses on what happens inside a subdomain, its business function, and logic. 


## business problem discovery
the software systems we are building are just solutions to business problems. In this context, the word problem does not resemble a mathematical problem or a riddle that you broader meaning a business problem can be challenges associated with optimizing workflows and processes, minimizing manual labor managing resources, supporting decisions managing data, and so on. Business problems appear both at the business domain and subdomain levels. A company's goal is to provide a solution for its customer's problems.

## knowledge discovery
To design an effective software solution, we have to grasp at least the basic knowledge of the business domain. the knowledge belongs to [[lddd - who are the domain experts|domain experts]] as it's their job in the first place, and it's crucial for us to understand domain experts and to use the same business terminology they use.
to be effective the software has to mimic the domain experts' way of thinking about the problem and their mental model. without an understanding of the business problem and the reasoning behind the requirements, our solutions will be limited to "translating" business requirements to code. and what if the requirements miss a crucial edge case? or fail to describe a business concept, limiting our ability to implement a model that will support future requirements? 
Effective knowledge sharing between domain experts and software engineers requires effective communication.

## communication
it's safe to say that almost all software projects require the collaboration of stakeholders in different roles (domain experts, product owners, engineers, designers) as in any collaborative effort the outcome depends on how well all those parties can work together. for example, do all stakeholders agree on what problem is being solved? what about the solution they are building do they hold any conflicting assumptions about its functional and non-functional requirements? agreement and alignment on all project-related matters are essential to a project's success.
yet despite the importance of effective communication in the project success, it is rarely observed in software projects, often businesspeople and engineers have no direct interaction with one another, instead domain knowledge is pushed down from domain experts to engineers, and it is delivered through people playing the role as mediators or translators systems/business analysts or product owners. 
during this traditional software development lifecycle, the domain knowledge is translated into an engineer-friendly form known as an analysis model, which is a description of the system requirements rather than an understanding of the business domain behind it. such mediation is hazardous to knowledge sharing because in any translation there's information is lost and in this case, it is domain knowledge that is essential for solving business problems. also often these documents got out of date quickly. 


## [[ubiquitous language|what is ubiquitous language]]

## [[lddd - using the ubiquitous language]]

## [[lddd - converting business domain to a model]]



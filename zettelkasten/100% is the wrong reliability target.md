---
tags:
  - SRE
related: "[[Site Reliability Engineering|SRE]]"
type:
  - fleeting
---
There are many tradeoffs you have to consider when setting a reliability target
if you are trying to run your service much more reliably than it needs to be you are slowing down development velocity for features that will make your customers happier for a minor increase in reliability. 100% is the wrong reliability target for everything 

to choose the right target for your reliability here are some things to think about first you are going to want to have ambitious but achievable targets![[Screenshot 2023-12-17 at 20.19.38.png]]

there is not actually a linear relationship between service availability and user happiness once you have passed [[the happiness test]] increasing availability will have diminishing returns in addition higher availability costs you more to provide, reducing your ability to make changes and release new features 
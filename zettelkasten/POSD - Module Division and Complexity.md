---
tags:
  - book-notes
  - software-design
type:
  - literature
related: "[[POSD - better together or better apart]]"
---

**when** deciding whether to combine or separate, the goal is to reduce the complexity of the system as a whole and improve its modularity.
it might appear that the best way to divide the system into a large number of small components, the smaller the components the simpler each component is likely to be however the act of subdividing creates additional complexity that was not present before subdivision:
- some complexity comes just from the number of components: the more components the harder to keep track of them all and the harder to find a desired component within the large collection. subdivision usually results in more interfaces. and every new interface adds complexity.
- subdivision can result in additional code to manage the components. for example, a piece of code that used a single object before subdivision might now have to manage multiple objects.
- subdivision creates separation: the subdivided components will be farther apart than they were before the subdivision. for example, methods that were together in the same class may be in different classes after subdivision and possibly in different files, separation makes it harder for developers to see the components at the same time, or even to be aware of their existence.
- subdivision can result in duplication: code that was present in a single instance before subdivision may need to be present in each of the subdivided components.

**But if the components are truly independent then separation is good**: it allows the developer to focus on a single component at a time without being distracted by the other components on the other hand if there are dependencies between components then separation is bad as developers will end up flipping back and forth between the components. even worse they may not be aware of the dependencies which can lead to bugs.
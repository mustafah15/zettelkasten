---
tags:
  - software-design
parent: "[[different layer different abstraction]]"
type: permanent
deeper: "[[why pass-through methods are bad]]"
related: "[[pass-through variables]]"
---
When adjacent layers have similar abstractions, the problem often manifests itself in the form of pass-through methods.

The definition of a pass-through method is o**ne that does little except invoke another method whose signature is similar or identical to that of the calling methods**.

If a pass-through method does nothing except pass its arguments to another method, usually with the same API as the pass-through method. this indicates that there is not a clean division of responsibility between the classes.

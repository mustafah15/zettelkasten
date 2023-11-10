---
tags:
  - software-design
type:
  - fleeting
related: "[[POSD - different layer different abstraction]]"
---

- a dispatched is a method that uses its arguments to select one of several other methods to invoke; then it passes most or all of its arguments to the chosen method.
- dispatcher example
	- when a web server receives an incoming request from a browser it invokes a dispatcher that examines the url in the incoming request and selects a specific method to handle the request.
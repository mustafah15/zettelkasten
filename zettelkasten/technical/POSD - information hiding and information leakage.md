---
tags:
  - software-design
  - book-notes
related: "[[philosophy of software design]]"
type: reference
---
[[POSD - information hiding]]
[[POSD - information leakage]]
[[POSD - temporal decomposition]]

information hiding only makes sense when the information being hidden is not needed outside its module. if the information is needed outside the module then you must not hide it.
suppose that the performance of a module is affected by certain configuration parameters and that different uses of the module require different settings of the parameters and that will require different settings of the parameters. in this case, it is important that the parameters are exposed in the module's interface so that they can be tuned appropriately.
As a software designer, your goal should be to minimize the amount of information needed outside a module. Still, it is important to recognize which information is needed outside the module and make sure it is exposed.


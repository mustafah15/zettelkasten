---
title: taking it too far
---

- information hiding only makes sense when the information being hidden is not needed outside its module. if the information is needed outside the module then you must not hide it. 

- suppose that the performance of a module is affected by certain configuration parameters and that different uses of the module require different setting of the paramters and that dwill require different settings of the parameters. in this case it is important that the paramters are exposed in the interface of the module, so that they can be turned appropriately. 

- As software designer your goal should be minimize the amount of information needed outside a module but it is important to recognize which information is needed outside module and make sure it is exposed. 

- 

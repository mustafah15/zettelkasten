---
tags:
  - software-design
type: literature
parent: "[[information hiding|information hiding]]"
---

information hiding reduces complexity in two ways.
- first, it simplifies the interface to a module so the interface reflects a simpler more abstract view of the module's functionality and hides the details this reduces the [[cognitive load]] on developers who use the module.
- second, information hiding makes it easier to evolve the system. If a piece of information is hidden, there are no dependencies on that information outside the module, so a design change related to that information will affect only one module.
when designing a new module, you should think carefully about what information can be hidden in that module. if you can hide more information, you should also be able to simplify the module's interface, and this makes the module deeper.

hiding variables and methods in a class by declaring them private isn't the same thing as information hiding as private items can still be exposed through public methods such as getter and setter methods. when this happens the nature and usage of the variables are just exposed as if the variable were public.

the best form of information hiding is when information is totally hidden within a module so that it is irrelevant and invisible to users of the module. however partial information hiding also has a value. for example, if a particular feature or piece of information is only needed by a few of the class's users and it is accessed through a separate method so that it isn't visible in the most common use cases, then that information is mostly hidden such information will create fewer dependencies than information that is visible to every user of the class.


---
tags:
  - book-notes
  - software-design
parent: "[[philosophy of software design]]"
type: reference
---
Its more important for a module to have a simple interface than a simple implementation

As a developer it's tempting to behave in the opposite fashion to solve the easy problems and punt the hard ones to someone else. of a condition arises that you are not certain how to deal with the easiest thing is to throw an exception and let the caller handle it, if you not certain what policy to implement, you can define a few configuration parameters to control the policy and leave it up to the system administrator to figure out the best values for them.

Approaches like these will make your life easier in the short term, but amplify complexity so that many people must deal with a problem rather than just one person. for example, if a class exports configuration parameters every system administrator in every installation will have to learn how to set them.

EXAMPLE: Configuration Parameters.
- configuration params are an example of moving complexity upwards instead of down. rather than determining a particular behavior internally, a class can export a few parameters that control its behavior, such as the size of a cache or the number of times to retry a request before giving up. users of the class must then specify appropriate values for the parameters.
- Advocates argue that configuration parameters are good because they allow users to tune the system for their particular requirements and workloads, in some situations it's hard for low-level infrastructure code to know the best policy to apply, a decision that needs users who are much more familiar with their domain.
- However, Configuration parameters also provide an easy excuse to avoid dealing with important issues and pass them on to someone else, in many cases it's difficult for users or administrators to determine the right values for the parameters. In other cases, the right values could have been determined automatically work a little extra work in the system implementation.

you should avoid configuration parameters ask yourself will users or higher level modules be able to determine a better value than we can determine here? when you do create configuration parameters see if you can compute reasonable defaults automatically, so users will only need to provide values under exceptional conditions. ideally, each module should solve a problem completely; configuration parameters result in an incomplete solution which in the end adds to system complexity.

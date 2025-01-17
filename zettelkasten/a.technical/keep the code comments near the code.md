---
tags:
  - system-design
type: literature
parent: "[[modifying existing code|modifying existing code]]"
---

### keep the comments near the code
- when you change existing code there's a good chance that the change with invalidate some of the existing comments. it's easy to forget to update comments when you modify code, which results in no longer accurate comments. inaccurate comments are frustrating to the reader begin to distrust all of the comments. fortunately, with a little disipline and a couple of guiding rules it's possiple to keep comments up-to-date without a huge effort.
- the best way to ensure that comments get updated is to position them close to the code they describe, so developers will see them when they change the code. the farther a comment is from its associated code, the less likely it is that it will be updated properly.
- when writing implementation comments don't put all the comments for an entire method at the top of the method, spread them out, pushing each comment down to the narrowest scope that includes all of the code referred to by the comment for example if a method has three major phases don't write one comment at the top of the method describes all of the phases in detail instead write a separate comment for each phase and position that comment just above the first line of code in that phase.
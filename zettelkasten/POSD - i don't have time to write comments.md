---
tags:
  - book-notes
  - system-design
related: "[[philosophy of software design]]"
type:
  - literature
---
- Given a choice between adding a new feature and documenting an existing feature, it seems logical to choose the new feature however, software projects are almost always under time pressure, and there will always be things that seem higher priority than writing comments. thus if you allow documentation to be de-prioritized you will end up with no documentation at all
- The counter-argument to this excuse is the [[POSD - strategic programming]] and its investment mindset if you want a clean software structure, which will allow you to work efficiently over the long-term, then you must take some extra time upfront in order to create that structure.

- good comments make a huge difference in the maintainability of software so the effort spent on them will pay for itself quickly, furthermore writing comments needn't take a lot of time.
- With these assumptions writing good comments won't add more than about 10% to your development time and the benefits of having good documentation will quickly offset this cost.
- Furthermore, many of the most important comments are those related to abstraction such as the top-level documentation for classes and methods. these comments should be written as part of the design process, and the act of writing the documentation serves as an important design tool that improves the overall design. these comments pay for themselves immediately
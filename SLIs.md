---
tags:
  - SRE
type:
  - fleeting
related: "[[observability]]"
aliases:
  - service level indicators
---
### What is an SLI?

An SLI (service level indicator) measures compliance with an SLO (service level objective). So, for example, if your SLA specifies that your systems will be available 99.95% of the time, your SLO is likely 99.95% uptime and your SLI is the actual measurement of your uptime. Maybe it’s 99.96%. Maybe 99.99%. To stay in compliance with your SLA, the SLI will need to meet or exceed the promises made in that document.

### The challenges of SLIs

As with SLOs, the challenge of SLIs is keeping them simple, choosing the right metrics to track, and not overcomplicating IT’s job by tracking too many metrics that don’t actually matter to clients.

### Who needs SLIs?
Any company measuring their performance against [[SLOs]] needs SLIs in order to make those measurements. You can’t really have [[SLOs]] without SLIs.


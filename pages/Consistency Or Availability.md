---
title: Consistency Or Availability
---

- Consistency Or Availability In Distributed Systems
id:: 75bcd897-6707-49bd-bb86-94905e56a489
	 - the [[CAP Theorem]] but us in a situation where we have to make a choice between [[strong consistency]] and [[Availability]] this is a challenge because ideally, we want both all the time but we can't have that, that what [[CAP Theorem]] tells us, so now the question is how to decide whether we aim for [[strong consistency]] or whether we aim for [[Availability]] which one is more important.
id:: e18d28a1-e49b-4a74-9531-44dc34fd3202

	 - closing between [[strong consistency]] and [[Availability]] should not be a technical decision, as it's a business decision, the decision when and where to sacrifice consistency or availability should be discussed with a domain expert. as we will need to factor the impact of this decision on the business if the system is unavailable or eventually consistent.
id:: 34550340-0893-44bd-9da4-f20746281a9a

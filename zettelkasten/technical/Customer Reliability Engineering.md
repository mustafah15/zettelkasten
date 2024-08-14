---
tags:
  - SRE
related: "[[Site Reliability Engineering|SRE]]"
aliases:
  - CRE
type: permanent
---
# CRE = customer reliability engineering 
focusing on breaking organization barriers not between individual silos in a single company but instead between a cloud customer and its platform provider.
also help customers to implement SRE practices like SLOs and SLOs. 
also, it has to do with making failure a normal thing for instance make sure that everyone has SLOs and an error budget so you can communicate about what is an acceptable level of reliability so that everyone does not panic when there is a little bit of downtime 

# CRE's Three Reliability Principles 

### Reliability is the most important feature 
after all if your customers are unable to use the services you're providing they can't take advantage of any of the features you have so painstakingly built for them. 
on the other hand, this doesn't mean that the system should never fail its users. this is a costly and often unreachable target to set. a more realistic goal is that the system should meet the expectations of its users and strive to maintain their trust.
### Users not monitoring decide reliability 
if your system must show it is meeting its user's expectations of reliability then you have to measure their experience of its reliability 
if your users perceive your service to be unreliable then it's not meeting their expectations no matter your logs and metrics say.

### Well-engineered 
architecting a system carefully and following best practices for reliability like running in multiple globally distributed regions means that the system has the potential to achieve three nines (%99.9) over a long time horizon.
to reach four nines(%99.99), it's not enough to have talented developers and well-engineered software you also need an operations team whose primary goal is to sustain system reliability through both **reactive** like well-trained incident response and **proactive** like removing bottlenecks and automating processes and isolating failure domains 
each additional 9 makes your system 10 times more reliable than before, but as rough role of thumb, it also costs your business 10 times more. 
engineering a system to have reliability as its top priority means making many hard choices with  wide-ranging consequences for the business  
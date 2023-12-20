---
tags:
  - software-design
  - distributed-systems
type:
  - fleeting
---


- Availability In Distributed Systems
	- availability definition is that a system remains operational to perform its required function in a specific period. It is a simple measure of the percentage of time that a system, service, or machine remains operational under normal conditions.

- Reliability In Distributed Systems
	- A system is considered reliable if it keeps delivering its services even when one or several of its software or hardware components fail. Reliability represents one of the main characteristics of any distributed system since in such systems any failing machine can always be replaced by another healthy one, ensuring the completion of the requested task.

- How Reliability and Availability Are Related In A Distributed System
	- If a system is reliable, it is available. However, if it is available, it is not necessarily reliable. In other words, high reliability contributes to high availability, but it is possible to achieve a high availability even with an unreliable product by minimising repair time and ensuring that spares are always available when they are needed. Let’s take the example of an online retail store that has 99.99% availability for the first two years after its launch. However, the system was launched without any information security testing. The customers are happy with the system, but they don’t realize that it isn’t very reliable as it is vulnerable to likely risks. In the third year, the system experiences a series of information security incidents that suddenly result in extremely low availability for extended periods of time. This results in repetitional and financial damage to the customers.
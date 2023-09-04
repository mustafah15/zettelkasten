

tags: #software-design #distributed-systems 
type: #fleeting 

---



- **Definition**: the system continue to operate despite an arbitrary number of messages being dropped or delayed by the network.
- so the reality is no distributed system is safe from the partition, they can occur due to problems in the network, or just node can go down for one reason or another. so in any of those partition cases we have an interruption in our system communication, these interruption can be short or long-lived.
- [[CAP Theorem]] has more information how to a distributed system should deal with the partitions.
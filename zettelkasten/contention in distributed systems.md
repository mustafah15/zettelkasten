tags: #software-design #distributed-systems 
type: #literature  
relatedTo: [[scalability]]

--- 

What is contention?
- Any two requests that content for a single limited resource are in contention, this contention can only have one winner. other forced to wait for the winner to complete, as the number of things competing for increases the time to free up resources increases and eventually exceed acceptable time. As the number of things (requests) that competes for the resource increases the time to free up the resource increases. As the load increases, we will eventually exceed acceptable time limits.

How contention effect scalability?
see: [[amdahl's law]], [[gunther's universal law]]

As [[amdahl's law]] showed us the effect of contention on a distributed system and demonstrated that when we have contention as we try to add more parallelisation or as we try to scale up we start to see diminishing returns, there's another effect we have to take into account and that is [[the effect of coherency delay]]

Both [[amdahl's law]], [[gunther's universal law]] demonstrate [[linear scalability]] is almost unachievable Linear scalability requires total isolation, reactive systems understand the limitation imposed by these laws and accept them rather than avoid them.

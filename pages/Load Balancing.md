---
title: Load Balancing
---

- Load Balancer is another critical component of any distributed system. it helps to spread the traffic across a cluster of servers to improve responsiveness and availability of applications, websites or databases.

- LB also keeps track of the status of all the resources while distributing requests. if a server is not available to take new requests or not responding or has elevated error rate, LB will stop sending traffic to such server.

- Typically a load balancer sits between the client and the server accepting incoming network and application traffic and distributing the traffic across multiple backend server using various algorithms. by balancing application request across multiple servers, a load balancer reduces individual server load and prevents any one application server from becoming a single point of failure, thus improving overall application availability and responsiveness.

- To utilize full scalability and redundancy we can try to balance the load at each layer of the system. we can add LBs at three places.
	 - between the user and the web servers

	 - between the web servers and an internal platform layer like application servers or cache servers.

	 - between internal platform layer and database.

- ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2FeiF1oor9wx.png?alt=media&token=29a8f723-5221-4856-94c1-6b077f5e5c1f)

- **Benefits of load balancing**
	 - **Users experience faster uninterrupted service**. Users won't have to wait for a single struggling server to finish it's previous tasks. instead, their requests are immediately passed on to a more available resource.

	 - **Service Providers experience less down time and higher throughput**. even a full server failure won't affect the end user experience as the load balancer will simply route around it to a healthy server.

	 - load balancers makes it easer for system admins to handle in coming requests while decreasing wait time for users.

	 - smart load balancer provide benefits like predictive analytics that determine traffic bottlenecks before they happen. as a result the smart load balancer gives an organization actionable insights.

- **Load Balancing Algorithms**
	 - How Load balancer choose the backend server?

	 - Load balancer consider two factors before forwarding a request to a backend server.

	 - they will first **ensure that the server they choose is actually responding** appropriately to requests and then **use a pre configured algorithm to select one from the set of healthy servers**.

	 - There is a variety of load balancing methods which use different algorithms for different needs.
		 - **Least Connection Method** this method directs traffic to the server with the fewest active connection.

		 - **Least Response time Method** this method direct traffic to the server with the fewest active connections and the lowest average response time.

		 - **Least Bandwidth Method** this method select the server that is currently serving the least amount of traffic measured in megabits per second.

		 - **Round Robin Method** this method cycles through a list of servers and sends each new requests to the next server. when it reaches the end of the list, it starts over at the beginning.

		 - **IP Hash** under this method a hash of the ip address of the client is calculated to redirected the request to a server

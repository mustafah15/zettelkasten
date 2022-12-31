---
title: golden metrics for monitoring
---

- The golden signals
	 - A great place to start a monitoring solution is by implementing Google's four golden signals1. The golden signals are latency, traffic, errors, and saturation.

	 - Along with the golden signals are two supporting methods:
		 - The USE Method2: utilization, saturation, and errors. This method can analyze the performance of most any system.

		 - The RED Method3: rate, errors, and duration. This method focuses on service monitoring.

- Latency
	 - __Latency__ is the time that it takes to service a request, or the metric that is formally known as __response time__. It’s important to measure the latency from service to service and the latency that the user is experiencing. Establish a baseline for application normalcy with latency. It is a key indicator of degradation in the application.

	 - Don't use averages against latency, as they can be misleading. Rather, use histograms for this metric. Establishing percentile thresholds and values provide a better understanding of what the latency is. Values in the 95th or 99th percentile are key to detecting performance issues in a request or a component.

	 - Be sure to monitor the latency of errors, too. One bad long performing transaction can induce latency to the good requests, making for unhappy users.

- Traffic
	 - __Traffic__ is the amount of activity in the application. This value might be different depending on the characteristics of the application. Again, don't use averages. Examples of traffic include the number of requests that an API handled, the number of connections to an application server, and the bandwidth that was consumed to stream an application.

- Errors
	 - __Errors__ are the rate of requests that are failing. Monitoring explicit errors, such as HTTP 500s, is straightforward. You also need to "catch" the HTTP 200s that are sharing the wrong content. Measure errors in rates.

	 - Errors should expose bugs in the application, misconfigurations in the service, and dependency failures. Error rates can also affect other measurements, such as lowering latency or increasing saturation.

- Saturation
	 - __Saturation__ is how "full" your service is. The type of application that you're monitoring is directly related to the utilization metrics that you use to determine saturation. Saturation is the most challenging signal to implement. You need utilization metrics and the utmost flexibility to determine saturation.

	 - A few examples for determining saturation are as follows:
		 - CPU and memory for all applications

		 - Disk I/O rates for databases and streaming applications

		 - Heap, memory, thread pool garbage collection for Java™ applications

		 - 99th percentile for latency

	 - Keep in mind that the application services usually start to degrade before a metric reaches 100% utilization.

	 - It takes time to set up the signals for all the components in today’s applications. The easiest path is to shift left and begin monitoring and testing the application during the development and load-test phases, understanding the performance characteristics before the production rollout. For more information, see "Start performance testing early".

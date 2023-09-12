tags: #tools 
type: #fleeting  
relatedTo: [[distributed systems]]

---

[[monitoring]] vs. [[observability]] vs [[application performance management]]


Observability means distributed tracing that allows your system to receive a request and track that work as it interacts with various functions, and services that comprise your application.

observability contains the following 
- logging that can be from 
	- os 
	- k8s
	- application 
- metrics 
- tracing  

An aggregator collects all logs from the system, and it has filters so developers can look only for what they need


Trances generally consist of spans and each span has the following properties 
- span id
- parent span id
- trace id
- operation name

Some say that observability is the evolution of [[application performance management|APM]] however APM provides a debugging of an application and observability provides an understanding 

collect, monitor, analyze 

k8s add the following
service level objectives 
service level indicators 


### Events

What is an event?
	a timestamp and a collection of attributes.
example if you have an HTTP server what kind of events are you going to have?
- connection events 
- request events 
- response events
- etc
and all those events going to have different attributes associated with them like
- unique event attributes like
	- timestamp
	- description or message
- resource attributes (static context) like 
	- service name 
	- service id 
	- service version 
	- region
- operation attributes (dynamic context) like
	- request start time
	- request duration
	- http status 
	- http method
	- project id
	- account id
- causality attributes 
	- trace id 
	- span id 
	- parent span id 
	- operation name

Adding context turns events into traces which is super important because finding logs in a large distributed system is painful and suffering, Without context like `traceID` lots of searching and filtering is required, however finding all of the events in a trace is easy which can be a  single lookup.

### Aggregates 

When we look at events over time (aggregates) we want to find patterns and be alerted when bad patterns appear example the number of errors increasing over time, so we want to count how many times a specific attribute is showing up on an event, alternatively you can look a value of an attribute and see if it exceed a certain threshold that you know is bad for example latency 


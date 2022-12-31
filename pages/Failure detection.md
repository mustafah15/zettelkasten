---
title: Failure detection
---

- several things can go wrong when a client sends a request to a server in the happy path, the client sends a request and receives a response back. but what if no response comes back after some time? in this case, it's possible to tell whether the server is just **very slow, it crashed or a message couldn't be delivered because of a network issue** the worst case, the client will wait forever for a response that will never arrive, the best it can do is make an educated guess on whether the server is likely to be down or unreachable after some time has passed. to do that the client can configure a time out to trigger if it hasn't received a response from the server after a certain amount of time. if and when the timeout triggers, the client considers the server unavailable and throws an error.

- the tricky part is deciding how long to wait for the timeout to trigger. if the delay is too short the server is reachable, the client will wrongly consider the server deadly if the delay is too long and the server is down, the client will block waiting for a response, the bottom line is that it's not possible to build a perfect failure detector. a process doesn't necessarily need to wait to send a message to find out that the destination is not reachable. it can also actively try to maintain a list of processes that are available using pings or heartbeats.

- a ping is a periodic request that a process sends to another to check whether it's still available or not. The process expects a response to the ping within a specific time frame if no response is received, a time out triggered that marks the destination as down. however, the process will keep regularly sending pings to it si that if and when it comes back online it will be marked as available again.

- a heartbeat is a message that a process periodically sends to another to inform it that it's still up and running. if the destination does not receive a heartbeat within a specific time frame, it triggers a time out and marks the process that missed the heartbeat as dead. if that process comes later back to life and starts sending out heartbeats, it will eventually be marked as available again. 

- pings and heartbeats are typically used when a specific processes frequently interact with each other, and an action needs to be taken as soon as one of them are no longer reachable. if that's not the case detecting failures just at communication time is good enough.

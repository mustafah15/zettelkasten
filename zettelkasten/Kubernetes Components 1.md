---
tags:
  - kubernetes
  - infrastructure
type: fleeting
related: "[[Kubernetes]]"
---
when you are installing Kubernetes on the system you are actually installing the following components 
- **Api Server**: acts as the front end for Kubernetes users management devices command line interfaces all talked to the API server to interact with Kubernetes cluster
- **etcd service**: distributed key-value store used by Kubernetes to store all data used to manage the cluster
- **kubelet**: is the agent that runs on each node in the cluster, the agent is responsible for making sure that the containers are running on the node as expected
- **container runtime**: is the underlying software that is used to run containers (docker)
- **controller**: the brain behind or orchestration they're responsible for noticing and responding when nodes, containers, or endpoints go down.
- **scheduler**: is responsible for distributing work or containers across multiple nodes. 

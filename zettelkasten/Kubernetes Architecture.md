---
tags:
  - kubernetes
  - infrastructure
type:
  - literature
related: "[[Kubernetes]]"
---

## Node

A node may be a virtual or physical machine on which Kubernetes is installed a node is a worker machine and that is where containers will be launched by Kubernetes

What if a node that is running your application fails => and your application goes down you need to have more than one node

## Cluster 
A cluster is a set of nodes grouped together, this way if one node fails you have your application still accessible from the other nodes, having more nodes helps to share the load as well 

## Master Node
the master is another node with Kubernetes installed on it and it's configured as a master, the master watches over the other nodes in the cluster and is responsible for the actual orchestration of containers on the worker nodes.

## [[Kubernetes Pod]]


## Components 

when you are installing Kubernetes on the system you are actually installing the following components 
- **Api Server**: acts as the front end for Kubernetes users management devices command line interfaces all talked to the API server to interact with Kubernetes cluster
- **etcd service**: distributed key-value store used by Kubernetes to store all data used to manage the cluster
- **kubelet**: is the agent that runs on each node in the cluster, the agent is responsible for making sure that the containers are running on the node as expected
- **container runtime**: is the underlying software that is used to run containers (docker)
- **controller**: the brain behind or orchestration they're responsible for noticing and responding when nodes, containers, or endpoints go down.
- **scheduler**: is responsible for distributing work or containers across multiple nodes. 

## Master vs Worker Nodes

#### Master Node owns the following components 

- kube-apiserver
- etcd
- controller 
- schedular

#### Worker Node owns the following components 

- kubelet
- container run time

### kubectl
- is used to deploy and manage applications on Kubernetes cluster to get cluster info, and list all the nodes from a cluster.


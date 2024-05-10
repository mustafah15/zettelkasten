---
tags:
  - kubernetes
  - infrastructure
type:
  - literature
related: "[[Kubernetes]]"
---

## Kubernetes Pod

A pod is a single instance of an application, as Kubernetes does not deploy a container directly on a worker node the container is encapsulated into a Kubernetes object known as a pods

Note that a pod is the smallest unit you can create in Kubernetes, you shouldn't have multiple app **containers** in one pod, pods usually have a one-to-one relationship with containers running your application to scale up you add new pods to scale down you delete existing pods
exceptions to that are: 
- having helper containers to your main pod example having a sidecar to your pod

Note that you still can run multiple pods in a single node however, this is not desirable in prod env it still can happen if you have one bare-metal server with good specs.

## [[Pod YAML Definition]]
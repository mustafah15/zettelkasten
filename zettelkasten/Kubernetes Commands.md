---
tags:
  - kubernetes
  - infrastructure
related: "[[Kubernetes]]"
type: literature
---
- running a pod from image 
```bash
kubectl run <pod-name> --image=<image-name> --labels="key=value" --port=<port> --expose=true <this will create a clusterIp>
```

- create a service 
```bash
kubectl expose pod/service <pod-name/service-name> --port <port> --name <service name>
```


- create a deployment 
```bash 
kubectl create deployment <deployment-name> --image=<image-name> --replicas=<number-of-replicas>
```
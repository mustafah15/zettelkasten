---
tags:
  - kubernetes
  - infrastructure
type: permanent
parent: "[[Kubernetes]]"
---
A Kubernetes definition file always contains 
four top-level fields 
- `apiVersion`: this is the version of the Kubernetes API 
- `kind`: the kind refers to the type of object we are trying to create which in this case happens to be a pod. some other 
- `metadata`: is data about the object as its name tags, etc and it comes in the form of a dictionary
- `spec`: the specs define what is inside the object we are creating. 
these are the top-level or root-level properties these are also required fields so you must have them in your config file.

- To create an object from a file
```bash
kubectl create -f pod-definition.ymls
```

- To update an object from a file
```bash
kubectl replace -f pod-definition.ymls
```

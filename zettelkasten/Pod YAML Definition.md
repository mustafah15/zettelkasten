---
tags:
  - kubernetes
  - infrastructure
---

A Kubernetes definition file always contains 
four top-level fields 
- apiVersion: this is the version of the kubernetes API 
- kind: the kind refers to the type of object we are trying to create which in this case happens to be a pod. some other 
- metadata: is data about the object as its name tags, etc and it comes in a form of dictionary
- spec: for a pod it should be easy to specify for other objects its important to check the kubernetes docs.
	- containers:
		- name: nginx-container
		- image: nginx
these are the top-level or root-level properties these are also required fields so you must have them in your config file.


![[Screenshot 2024-04-22 at 20.38.01.png]]

to create a pod from a def file you can run this command 
```bash
	kubectl create -f pod-definition.ymls
```
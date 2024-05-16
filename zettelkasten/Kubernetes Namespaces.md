---
tags:
  - kubernetes
  - infrastructure
type: literature
---
Namespaces are intended for use in environments with many users spread across multiple teams, or projects. For clusters with a few to tens of users, you should not need to create or think about namespaces at all. Start using namespaces when you need the features they provide.


#### Initial Namespaces

 `default`

Kubernetes includes this namespace so that you can start using your new cluster without first creating a namespace.

`kube-public`

This namespace is readable by _all_ clients (including those not authenticated). This namespace is mostly reserved for cluster usage, in case that some resources should be visible and readable publicly throughout the whole cluster. The public aspect of this namespace is only a convention, not a requirement.

`kube-system`

The namespace for objects created by the Kubernetes system.


```YAML
apiVersion: v1
kind: Namespace
metadata:
	name: dev
```

to switch the name spaces 
you need to set the namespace in the current context to the new namespace

```bash
	kubectl config set-context $(kubectl config current-context) --namespace=new-namespace
```

to list all pods in all namespaces

use 

```bash 
kubectl get pods --all-namespaces
```


#### Resources


to limit resources in a namespace, create a resource quota to create one use a definition file 

```YAML
apiVersion: v1
kind: ResourceQuota
metadata:
	name: compute-quota
	namespace: dev
specs:
	hard:
		pods: "10"
		requests,cpu: "4"
		requests.memory: 5Gi
		limit.cpu: "10"
		limit.memory: 10Gi
```


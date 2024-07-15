---
tags:
  - kubernetes
  - infrastructure
parent: "[[Kubernetes Configuration]]"
type: permanent
---
it's the [[Kubernetes scheduler]] that decides which node a pod goes to, the schedular takes on consideration the amount of resources required by a pod and those available on the nodes and identifies the best node to place a pod on.

you can specify the amount of CPU and Memory when you spin up a new pod, to do this in pod-definition.yaml file you can put this under `spec`  you should add a section called `resources` and specify the required resources
you can also specify the limits where your application is not allowed to use more than that limit

```YAML
...
spec:
	containers:
	- name: web-app
	  resources:
		requests:
			mem: "1Gi"
			cpu: 2
		limits:
			mem: "2Gi"
			cpu: 4

```

you can also create a [limitrange resource object](https://kubernetes.io/docs/concepts/policy/limit-range/#limitrange-and-admission-checks-for-pods)

```yaml
apiVersion: v1
kind: LimitRange
metadata:
  name: cpu-resource-constraint
spec:
  limits:
  - default: # this section defines default limits
      cpu: 500m
    defaultRequest: # this section defines default requests
      cpu: 500m
    max: # max and min define the limit range
      cpu: "1"
    min:
      cpu: 100m
    type: Container
```

## resource quotas 
is also another way to create resource limits on namespace level, so a resource quota is a namespace level object


```Yaml

apiVersion: v1
kind: ResourceQuota
metadata: 
	name: resource-quota
spec:
	hard:
		requests.cpu: 2
		requests.mem: "1Gi"
		limits.cpu: 4
		limits.mem: "**2Gi**"
```
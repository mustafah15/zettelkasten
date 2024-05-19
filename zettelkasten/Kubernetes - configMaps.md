---
tags:
  - kubernetes
  - infrastructure
related: "[[Kubernetes Configuration]]"
type: literature
---

Defining a ConfigMap 

kubectl create -f config-map.yaml

```yaml 
apiVersion: v1
kind: ConfigMap
metadata:
	name: app-config
data:
	APP_COLOR: blue
	APP_ENV: prod
```

list config maps 

```kubectl get configmaps```

inject config map in a pod 


you can use spec.envFrom prop to specify the config map where the pod can read the config
example 

```yaml
apiVersion: v1
kind: Pod
metadata:
	name: my-webapp
spec:
	cotnainers:
	- name: my-webapp
	  image: my-webapp
	  ports:
		  - containerPort: 8080
	  envFrom:
	  - configMapRef:
	    name: app-config
```
---
tags:
  - kubernetes
  - infrastructure
related: "[[Kubernetes Configuration]]"
---
how to setup env variables in kubernetes 

```
docker run -e APP_COLOR=blue my-app
```


given a pod definition file, to set an environment variable  use the env property which is an array so every item under the env starts with a dash indicating an item in the array 


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
	  env:
	  - name:APP_COLOR
	    value: blue
```

env value types
plain key value like above 

or you can use [[Kubernetes - configMaps]] or [[Kubernetes - secrets]] in that case you can use it like this in pod config definition 

```
  env:
	  - name:APP_COLOR
	    valueFrom: configMapKeyRef:
// or 
	  env:
	  - name:APP_COLOR
	    valueFrom:
		    secretKeyRef: 
```

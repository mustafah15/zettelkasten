---
tags:
  - kubernetes
  - infrastructure
related: "[[Kubernetes Configuration]]"
type: literature
---
since we can configure some [[Docker Security]] options for docker images during the docker run command these options can be configured through Kubernetes as well. 

As we know in Kubernetes containers are incapsulated in pods, so you may choose to configure the security setting in a pod level or a container level if you configure it on a pod level the settings will carry over to all the containers wihin the pod, if you configure it on both pod and container, **the settings on the container will overwrite the settings on the pod** 


```YAML
apiVersion: v1
kind: Pod
metadata: 
	name: web-pod
specs: 
	containers:
		- name: ubuntu
		  image: ubuntu
		  command: ["sleep", "3600"]
		  securityContext:
		    runAsUser: 1000
		    capabilities:
		      add: ["MAC_ADMIN"]
```

if you move `securityContext` under spec: that will configure the security config on the pod level instead of having it on the container level as above 
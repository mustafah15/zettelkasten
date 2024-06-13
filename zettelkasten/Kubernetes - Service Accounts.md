---
tags:
  - kubernetes
  - infrastructure
related: "[[Kubernetes]]"
type: literature
---
There are two types of accounts in Kubernetes
- a user account for humans 
- a service accounts for machines
	- for example, account for Prometheus to collect cluster metrics or Jenkis to deploy services to the cluster.

to create a service account run the following command 
```bash
# this is to create a new service account 
kubectl create serviceaccount <service-account-name>

# this is to get service account token
kubectl describe serviceaccount <service-account-name>
```

when a service account is created it creates a new [[Kubernetes - secrets]] object with it to store the token inside it. 

this token can be used as an authentication bearer token when making rest calls to the Kubernetes API

If the application is deployed in the same cluster there's an easier way to access this token, by mounting the service token secrets as a volume inside the pod hosting the 3rd party app.

you can do that by specifying the service account in the pod definition 

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
	serviceAccountName: <service-account>
	# this is set to false if you want kubernetes to stop mounting default service account into your pod
	# automountServiceAccountToken: false
```


> [!NOTE] Note
> Kubernetes will automatically mount the default service account to your pods if you haven't explicitly disabled them by stating that automountServiceAccountToken: false under spec in pod definition file




since Kubernetes 1.24 a service account does not create a token automatically with it you have to do that manually. 
```
kubectl create serviceaccount <service-account-name>
kubectl create token <service-account-name>
```
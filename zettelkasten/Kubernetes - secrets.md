---
tags:
  - kubernetes
  - infrastructure
related: "[[Kubernetes Configuration]]"
type: permanent
---
since [[Kubernetes - configMaps]] store config data in un-encrypted format that's where the need for the secrets comes from the need to store passwords and sensitive info in encoded files format 

there are two ways to create a secrets 

- imperative way without creating a secret definition file 
```bash
kubectl create secret generic <secret-name> --from-litral=<key>=<value>

// from a file 

kubectl create secret generic <secret-name> --from-file=<path-to-file>
```

- declarative way by creating a secret definition file

```yaml 

apiVersion: v1
kind: secret 
metadata:
	name: app-secret
data:
	DB_HOST: mysql //this should be encoded 
	DB_PASSWORD: password // this should be encoded
```


you can inject this into the pod yaml config 

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
	  - secretRef:
	    name: app-secret
```


anyone able to create pods/deployments in the same namespace can access the secrets

consider third party secrets store provider 
like vault or GCP provider

### [[Managing Kubernetes secrets with vault]]

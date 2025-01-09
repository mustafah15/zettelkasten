---
tags:
  - kubernetes
  - infrastructure
type: permanent
---
the deployment provides us with the capability to upgrade the underlying instances seamlessly using a rolling update, undo changes, pause and resume changes as required. 

![[Screenshot 2024-05-14 at 06.25.46.png]]

The content of a deployment definition file is exactly similar to the [[Kubernetes - replication controller and replicaSets]] definition file except for the `kind` which is now going to be  `Deployment`

the deployment automatically creates a replicaSet which create pods 

```yaml

apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80

```
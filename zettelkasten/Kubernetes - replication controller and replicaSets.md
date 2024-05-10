---
tags:
  - kubernetes
  - infrastructure
related: "[[Kubernetes]]"
type: literature
---
what is a replica and why do we need a replication controller?

the replication controller helps us to run multiple instances of a single pod in a Kubernetes cluster to provide high-availability, even if you have a single pod the replication controller can help, by automatically bringing up a new pod when the existing one fails. another need for the replication controller is to have multiple pods to share the load across them 

#### replica set is the new recommended way to use a replication controller 

replication controller example 
```yaml 
# replication-controller-example.yml
apiVersion: v1
kind: ReplicationController
metadata:
  name: nginx
spec:
  replicas: 3
  selector:
    app: nginx
  template:
    metadata:
      name: nginx
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx
        ports:
        - containerPort: 80
```

a replica set example 

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: guestbook
    tier: frontend
spec:
  # modify replicas according to your case
  replicas: 3
  selector:
    matchLabels:
      tier: frontend
  template:
    metadata:
      labels:
        tier: frontend
    spec:
      containers:
      - name: php-redis
        image: us-docker.pkg.dev/google-samples/containers/gke/gb-frontend:v5
```

in a replica set a selector is required however in a replication controller it is not the case the controller will pick up the labels that were provided under the pod template section also in a replica set situation the replica set can control pods that were already created before even not by the replica set itself as long the label are matched 
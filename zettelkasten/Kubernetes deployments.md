---
tags:
  - kubernetes
  - infrastructure
type: literature
---
the deployment provides us with the capability to upgrade the underlying instances seamlessly using a rolling update, undo changes, pause and resume changes as required. 

![[Screenshot 2024-05-14 at 06.25.46.png]]

The content of a deployment definition file is exactly similar to the [[Kubernetes - replication controller and replicaSets]] definition file except for the `kind` which is now going to be  `Deployment`

the deployment automatically creates a replicaSet which create pods 
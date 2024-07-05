---
tags:
  - kubernetes
  - infrastructure
related: "[[Kubernetes Configuration]]"
type: literature
---
taints and tolerations tend to set restrictions on what pods can be scheduled on a node. 
### taints are set on nodes
to add taint to a node you need to execute the following command
`kubectl taint nodes node-name key=value:taint-effect`

There are three taint effect 
- NoSchedule => prevent pods from being scheduled on the node
- PreferNoSchedule => avoiding pods to be scheduled on the node
- NoExecute => new pods will not be scheduled on the node and existing pods on the node if any will be evicted if they do not tolerate the taint.

### toleration are set on pods

to add toleration on a pod you need to update the node definition file and in the spec section we will need to add a toleration section and move the same values that used to create the taints to definitions example would be 

```YAML

	toleration:
		-key: app
		operator: "Equal"
		value: "blue"
		effect: "NoSchedule"
```

---
tags:
  - infrastructure
  - kubernetes
type: literature
related: "[[Kubernetes Configuration]]"
---
in order to label a node you need to use the command 

`kubectl label nodes <name-of-node> <label-name>=<label-value>`
example 

`kubectl label nodes  node1 size=large`


now that we have labeled the node we can get back and make the node selector on the pod 

under the spec section in pod def file need to add the following section 

```Yaml 
nodeSelector: 
	size: large
```

when the pod is now created it is placed on node 1 as desired "selected"

node selector has limitations 
for example what if we want to set a rule to place the pod on a large or medium node, or not small. for this we can't use node selector instead we should use [[Kubernetes - Node Affinity]] 
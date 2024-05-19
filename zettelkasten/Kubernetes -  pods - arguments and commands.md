---
tags:
  - kubernetes
  - infrastructure
related: "[[Kubernetes Configuration]]"
---
In the [[docker]] world, we would run the docker run command with the `--entrypoint` option set to whatever command that we want to use to start our container with, the corresponding entry in the pod definition file would be using a `command:` field inside the `spec.container` section also to pass an argument to the docker image you can add this inside an `args:` field inside the same `spec.containers` section

![[Screenshot 2024-05-17 at 07.22.17.png]]
---
tags:
  - docker
  - infrastructure
type: permanent
related: "[[Kubernetes]]"
---

## process isolation 
docker host running a docker container sharing the same kernel however it is separated by the namespace (host has it's own namespace, and docker has it's own namespace) all the process running in the container are in fact running on the host itself, 

however docker container can only see its only process that runs on its namespace however if you list the process in the host you will see the docker container process but with a different process ID, this is because the process can have different ids in different namespaces and that's how docker isolates container within the system 

## User

by default docker runs command with in container as the root user, If you don't want the container to run commands as the root user you may set the user using USER option within Dockerfile(image) or docker run command, 

#### Is the root user within the container the same as the root user in the host?

docker implements a set of security features that limits the ability of the root user within the container, so the root user within the container is not really like the root user on the host, however it's still preferable to use another user while creating/building a new docker image 
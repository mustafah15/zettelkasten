---
tags:
  - infrastructure
related: 
type: permanent
---
### building a new docker image from a file 

```
	docker build Dockerfile -t mhussain/my-custom-app
```

to make it available in the docker registry 

```
	docker push mhussain/my-custom-app
```


## docker layered architecture 

each line of instruction creates a new layer in the docker image with just the change from the pervious layer. 

each layer store the changes from the previous one, it's reflected in the size as well, you can see this information if you run the docker history command 

```
	docker history mhussain/my-custom-app
```

when you run the docker build command you can see the various steps involved and the result of each task, all the layers built are cashed, so the layer architecture helps you restart the docker build from that particular step in case it fails or you want to add a new steps in the build process you wouldn't have to start all over again.


### [[Docker Security]]


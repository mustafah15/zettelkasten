---
tags:
  - docker
type: permanent
---



```
docker run \                         
--name local-mysql \-p 33061:3306 \  
-e MYSQL_ROOT_PASSWORD=p4ssw0rd \  
-e MYSQL_DATABASE=app \  
-d mysql:latest
```

db url should be this at this case

`mysql://root:password@127.0.0.1:33061/app`

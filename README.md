## RUN VS CMD
RUN: This is called when we make docker image. ( we can do the commands like npm install and we can have multiple run commands..)  
CMD: entry point command (ex: node index.js) and this can be override when we run container

## Using alpine tag in docker image
You can reduce the image size dramatically by using alpine tag images from docker hub.
Please check [this link](https://alpinelinux.org/) out to know about the alpine.


## Tagging and Versioning
If you are using latest tag for the image, it could be changed later.
For example, if you used node:latest (let's say node version is 10 at this point)
but when you use that later, node version could be like 15 and it could break your code to not work with the latest version.

before
> FROM node:latest

after
> FROM node:specific_tag_here


## Tagging own image

> docker build -t imagename:latest .  
> docker tag imagename:latest imagename:1

This will genereate image which has version 1 from latest

## DOCKER REGISTRIES

> docker login  



> docker push username/imagename:version

this is just convenience and you can name it yourself.


## Docker Inspect

> docker inspect container_id

## Docker Logs
> docker logs container_id

> docker logs -f container_id

You can see the logs immediately without running docker logs again by using -f parameter.


## Docker exec
> docker exec -it container_id /bin/sh

You can open bash of docker. actually docker exec will run the program inside the docker container


--------
# KUBERNATES

kubernate is one of the most popular container orchestration system for docker containers.





































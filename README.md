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


## Master
API server: entrypoint to K8S cluster  
Controller manager: keeps  track of whats happening in the cluster
Scheduler: ensures Pods placement  
etcd: Kubernetes backing key-value store

## Worker
kublet will be running on it and few containers



## Pod, Conatiner, Service (internal, external), Ingress  
## ConfigMap
Don't put credentials into ConfigMap

## Secret
You can store the secret data like credentials here. (base64 encoded)  
(! The built-in security mechanism is not enabled by default.)

## Volumns


## Deploying Statefulset

## COMPONENTS SUMMARY

## Minikube and kubectl

### Minikube
To test the production cluster setup on localhost
- creates virtual box on your laptop  
- Node runs in that virtual box  
- 1 node K8s cluster  
- for testing purposes

### kubectl
command line tool to use to interact with any type of cluster

### Installing Minikube


```
brew upate
brew install hyperkit
brew install minikube
```
> minikube will install kubectl as a dependencies  
> minikube has docker runtime or docker deamon inside it.  
> If you installed docker for desktop, you will already have hyperkit.


> we will create called 'deployment' when we need 'pod' becuase in kubernates we will not work with 'pod' direclty. 'deployment' is the absctraction of 'pdf' and it will have 'pod' in it.

```shell
 minikube start --vm-driver=docker
 kubectl create deployment [name here] --image=nginx
 kubectl get deployment
 kubectl get pod
 ```
## debugging
```
kubectl logs [pod name]
kubectl describe pod [pod name] 
kubectl exec -it [pod name] -- bin/bash # -it means interactive terminal

```

## apply

```
kubectl apply -f [yaml file name]
kubectl delete -f [yaml file name]
```

## kubectl command summary



## Train (mongo & mongo-express)

see the folder train_kubernates

```
cd train_kubernates
kubectl apply -f mongo-configmap.yaml
kubectl apply -f mongodb-secret.yaml
kubectl apply -f mongo.yaml
kubectl apply -f mongo-express.yaml

minikube service mongo-express-service
```































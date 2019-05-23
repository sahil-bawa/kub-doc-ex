# Kubernetes Docker Example Setup
This code can be used to run an application on a kubernetes setup using docker on MacOS.

## Kubernetes Introduction
Kubernetes is a portable, extensible open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.

(Source: https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/)

## Install Kubernetes On Docker Mac
Download and install Docker for Mac from here: https://docs.docker.com/docker-for-mac/install/
Download and Install kubectl (Kubernetes Command Line Tool) here: https://kubernetes.io/docs/tasks/tools/install-kubectl/
Docker Preferenes and start Kubernetes from the Kubernetes tab. This may take a while.

### When Kubernetes is up and running, check kubernetes cluster info.

``` 
$ kubectl version
$ kubectl cluster-info
```

### Running a Webserver:
``` 
$ kubectl run —-image=nginx webserver-yourname
```
### Check your nginx deployment, ReplicaSet, and pods:
```
$ kubectl get deploy
$ kubectl get rs
$ kubectl get pod
```

### Port Forward from container to your local system:
``` 
$ kubectl get pod
$ kubectl portforward <pod-name> 5000:80
```
### Expose the node outside of the cluster:
``` 
$ kubectl expose deploy webserver-yourname --type=NodePort
$ kubectl get services
```
^ This expose command will assign a random port to your webserver. Let's call it <rand-port>.

Access the node port at localhost:<rand-port>

### Apply:
``` 
$ kubectl apply -f deployment.yaml
```

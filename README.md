# Kubernetes Docker Example Setup
This code can be used to run an application on a kubernetes setup using docker on MacOS.

## Kubernetes Introduction
Kubernetes is a portable, extensible open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.

(Source: https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/)

## Install Kubernetes On Docker Mac
Download and install Docker for Mac from here: https://docs.docker.com/docker-for-mac/install/
Download and Install kubctl (Kubernetes Command Line Tool) here: https://kubernetes.io/docs/tasks/tools/install-kubectl/
Docker Preferenes and start Kubernetes from the Kubernetes tab. This may take a while.

### When Kubernetes is up and running, check kubernetes cluster info.

``` $ kubectl cluster-info
$ kubectl version
```

### Running a Webserver:
``` $ kubectl run —-image=nginx webserver-yourname
```
### Port Forward:
``` $ kubectl get pods
$ kubectl portforward POD 5000:80
```
### Expose:
``` $ kubectl expose deploy/kubernetes-node --type=NodePort
$ kubectl get services
```
### Apply:
```$ kubectl apply -f deployment.yaml
```

## Installation

```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/darwin/arm64/kubectl"
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/darwin/arm64/kubectl.sha256"
echo "$(cat kubectl.sha256)  kubectl" | shasum -a 256 --check
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
sudo chown root: /usr/local/bin/kubectl
kubectl version --client
kubectl version --client --output=yaml
brew install minikube
```

### Minikube Basic Controls

```bash
minikube start
minikube dashboard
```

### Kubernetes Terninology

> Kubernetes Cluster

A collection of nodes + a master to manage them

> Node

A virtual machine that will run our containers

> Pod

More or less a running container, technically
a pod can run multiple containers

> Deployment

Monitor a set of pods, make sure thery are
running and restarts them if they crash

> Service

Provides an easy-to-remember URL to
access a running container

### Kubernetes Command

```bash
kubectl apply -f post.yaml
```

```bash
minikube start --vm=true
minikube stop
minikube delete
```

```bash
kubectl version -o json
kubectl version --client -o json
kubectl apply -f posts.yaml
kubectl get pods
kubectl delete -f posts.yaml
kubectl get deployments
kubectl get events
kubectl config view
kubectl get deployments
kubectl delete deployment [depl_name]
kubectl describe deployment [depl_name]
kubectl logs -f [pod_name]
kubectl exec -it [pod_name] sh/bash
kubectl rollout restart deployment [depl_name]
kubectl get services
kubectl apply -f .
```

| No  | Docker Commands                        | Kubernetes Commands                 |
| --- | -------------------------------------- | ----------------------------------- |
| 1   | docker ps                              | kubectl get pods                    |
| 2   | docked exec -it [container_id] sh/bash | kubectl exec it [pod_name] sh/shell |
| 3   | docker logs -f [container_id]          | kubectl logs -f [pod_name]          |
| 4   | docker rm [container_id]               | kubectl delete pod [pod_name]       |
| 5   | docker-compose -f [file_name]          | kubectl apply -f [config_file_name] |
| 6   | --                                     | docker describe pod [pod_name]      |

In MacOS [Slicon Chip], use the docker desktop for the kubernetes,
Minikube not working properly

### Types of Services

> Cluster IP

Sets up an easy-to-remember URL to assess a pod. Only exposes the pods in the cluster

> Node Port

Makes a pod accessible from outside the cluster. Usually only for dev purposes

> Load Balancer

Makes a pod accessible from outside the cluster. This is the right way to expose a pod to the outside world

> External Name

Redirects an in-clust request to a CNAME url.


### Load Balancer Service Vs Ingress

> Load Balancer Service

* Tells kubernetes to reach out to its provider and provision a load balancer.
* Get traffic to a single pod


> Ingress

* A pod with a set of routing rules to distribute traffic to other services


### Ingress Nginx

* A project that will create a load balancer service and an ingress for us


```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.3.0/deploy/static/provider/cloud/deploy.yaml
```

### Run Kubernets in localhost for [MacOS/Linux]

> /etc/hosts

```bash

127.0.0.1 posts.com

```
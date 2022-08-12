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

### Minikub Basic Controls

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


### Kebernets Command

```bash
kubectl apply -f post.yaml
```
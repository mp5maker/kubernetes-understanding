```bash
minikube start --vm=true
minikube stop
minikube delete
kubectl version -o json
kubectl version --client -o json
kubectl apply -f posts.yaml
kubectl get pods
kubectl delete -f posts.yaml
kubectl get deployments
kubectl get events
kubectl config view
```

| No | Docker Commands | Kubernetes Commands |
| -- | -- | -- |
| 1 | docker ps | kubectl get pods |
| 2 | docked exec -it [container_id] sh/bash | kubectl exec it [pod_name] sh/shell |
| 3 | docker logs -f [container_id] | kubectl logs -f [pod_name] |
| 4 | docker rm [container_id] | kubectl delete pod [pod_name] |
| 5 | docker-compose -f [file_name] | kubectl apply -f [config_file_name] |
| 6 | -- | docker describe pod [pod_name] |


In MacOS [Slicon Chip], use the docker desktop for the kubernetes,
Minikube not working properly
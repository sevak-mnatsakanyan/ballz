# K8 cheat sheet


```bash
# azure cli
az login
az account
az account show
az account list
az account set -s "id_or_name"

# clear all subscriptions from the CLI's local cache.
az account clear
```

```bash
# AKS
az aks get-credentials --resource-group <clusterRG> --name <cluster>
```

```bash
# manage k8 configurations
kubectl config view
kubectl config get-contexts
kubectl config use-context Cluster

# see status of the cluster
kubectl cluster-info
kubectl cluster-info dump

# list objects
kubectl get namespaces
kubectl get pods -n <namespace>
kubectl get pods -L app -n <namespace>
kubectl get ingress -n <namespace>
```

```bash
# pod diagnostics
kubectl exec <pod> -it -n <namespace> -- bash
kubectl port-forward <pod> <sourcePort>:<destinationPort> -n <namespace>
kubectl logs <pod-name> -c <init-container-2>
```

```bash
# scaling
kubectl scale deployment <name> --replicas=3
```

```bash
# helm 
helm lint
helm template ./<chartPath>
az acr helm delete -n <registryname> <chartName> --version <version>
```

```bash
# docker
docker ps -a
docker images
docker rmi <imagename>
```

```bash
# minikube usage
minikube dashboard
minikube ip
minikube service <serviceName>
```

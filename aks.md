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
kubectl config set-context <cluster> --namespace=<namespace-name>

# see status of the cluster
kubectl api-versions
kubectl cluster-info
kubectl cluster-info dump

# list objects
kubectl get namespaces
kubectl get pods -n <namespace>
kubectl describe pods -n <namespace>
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
# deployment
kubectl apply -f <deployment-file>.yaml -n <namespace>

# rollout
kubectl rollout status deployment.v1.apps/<serviceName> -n <namespace>
kubectl rollout history deployment.v1.apps/<serviceName> -n <namespace>

# scaling
kubectl scale deployment <name> --replicas=3
```

```bash
# resource management
kubectl get deployments --all-namespaces -o jsonpath="{range .items[*]}{.metadata.name}{'\t'}{..limits.cpu}{'\t'}{..requests.cpu}{'\n'}{end}"
kubectl get deployments --all-namespaces -o custom-columns=Name:.metadata.name,Limit:..limits.cpu,Request:..requests.cpu

# create a job from cronjob
kubectl create job --from=cronjob/<cronjob-name> <new-customjob-name> -n kube-system
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

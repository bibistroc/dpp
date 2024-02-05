# Namespaces

In Kubernetes, namespaces provides a mechanism for isolating groups of resources within a single cluster. Names of resources need to be unique within a namespace, but not across namespaces. Namespace-based scoping is applicable only for namespaced objects (e.g. Deployments, Services, etc) and not for cluster-wide objects (e.g. StorageClass, Nodes, PersistentVolumes, etc).

## Get namespaces

`kubectl get namespace`

or

`kubectl get ns`

## Create namespace

`kubectl create namespace <namespace>`

or

`kubectl apply -f namespace.yaml`

## Set current namespace

`kubectl config set-context --current --namespace=<namespace>`

### Credits
- [K8S](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/)
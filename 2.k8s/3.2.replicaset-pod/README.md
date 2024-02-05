# Replicaset

A `ReplicaSet` ensures that a specified number of pod replicas are running at any given time. However, a `Deployment` is a higher-level concept that manages ReplicaSets and provides declarative updates to Pods along with a lot of other useful features. Therefore, we recommend using `Deployments` instead of directly using `ReplicaSets`, unless you require custom update orchestration or don't require updates at all.

## Get replicasets

`kubectl get replicaset`

or

`kubectl get rs`

## Create replicaset

`kubectl apply -f replicaset.yaml`

## Edit replicaset

```bash
# Edit the entire replicaset config
kubectl edit replicaset/nginx-rs

# Edit the image
kubectl set image replicaset/nginx-rs nginx=nginx:1.16.1

# Scale de replicaset
kubectl scale rs/nginx-rs --replicas=10
```
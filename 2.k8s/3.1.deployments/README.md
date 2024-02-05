# Deployments

A Deployment provides declarative updates for Pods and ReplicaSets.

You describe a desired state in a Deployment, and the Deployment Controller changes the actual state to the desired state at a controlled rate. You can define Deployments to create new ReplicaSets, or to remove existing Deployments and adopt all their resources with new Deployments.

## Get deployments

`kubectl get deployments`

or

`kubectl get deploy`

## Create deployment

`kubectl apply -f deployment.yaml`

## Get status of deployment

`kubectl rollout status deployment/nginx-deployment`

## Edit a deployment

```bash
# Edit the entire deployment config
kubectl edit deployments/nginx-deployment

# Edit the image
kubectl set image deployments/nginx-deployment nginx=nginx:1.16.1

# Scale the deployment
kubectl scale deployment/nginx-deployment --replicas=10
```
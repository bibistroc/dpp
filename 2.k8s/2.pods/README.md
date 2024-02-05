# Pods

Pods are the smallest deployable units of computing that you can create and manage in Kubernetes.

A Kubernetes Pod is like a cozy little home for your application. It's a fundamental unit of deployment in Kubernetes, where all the magic happens. A Pod is a group of one or more containers that share common resources and run together on a single node. Think of it as a lightweight, atomic unit that encapsulates your application's processes, storage, and networking.

One of the main advantages of using Pods is their ability to enable coexistence. By running multiple containers within a single Pod, you can ensure that they work harmoniously together. These containers share the same IP address, port space, and local network, allowing them to communicate seamlessly. This coexistence ensures that all the necessary components of your application, such as a web server and a database, can work in perfect harmony.

## Get pods

`kubectl get pods`

or

`kubectl get po`

## Create pods

`kubectl apply -f pod.yaml`

## Kill pods

`kubectl delete pod nginx`

> **Notice**: the pod is not recreated because is not tied to a replicaset

## Portforward (for debug)

If the pod expose a port (containerPort) you can access that port using `port-forward`:

```bash
# This will bind the container port 80 to local port 8000
kubectl port-forward pod/nginx 8000:80
```

> **Warning**: This should only be used for development purposes

### Credits
- [Zeet.co](https://zeet.co/blog/kubernetes-deployment-vs-pod)
- [K8S](https://kubernetes.io/docs/concepts/workloads/pods/)
# Services

## Get services

`kubectl get services`

or

`kubectl get svc`

## Get endpoints

`kubectl get endpoints`

or

`kubectl get ep`

## Service types

### Cluster IP

Use this Service type when you want to expose an application within the cluster and allow other Pods within the cluster to access it.

### NodePort

Use this Service type when you want to expose your application on a specific port on each worker node in the cluster, making it accessible to external connections (coming from outside the cluster). NodePort Services are often used for development and testing purposes.


### Loadbalancer (out of scope)

Use this Service type when you want to expose your application to external clients. Sounds like the same thing mentioned for NodePort. But, there's the added benefit. You take advantage of a cloud provider's load balancing capabilities. And all client requests can be smoothly load balanced to multiple nodes in your cluster.

LoadBalancer Services are typically used in production environments. Why? One big reason is the increased reliability. When clients connect to one node specifically (through NodePort), if that node fails, the clients will be left hanging. Their requests will remain unfulfilled as the node is unreachable.

But, with a LoadBalancer, if one node fails, the LoadBalancer doesn't rely on a single node (it sends traffic to all). So only a few requests hitting the problematic node will fail, not all.

And with proper health checks in place, the LoadBalancer can stop sending traffic to the failed node. So future client requests can all land on healthy nodes.

### Credits
- [KodeKloud](https://kodekloud.com/blog/clusterip-nodeport-loadbalancer/)
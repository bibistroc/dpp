# Setup kind

## Install kind

[KinD Website]([KinD](https://kind.sigs.k8s.io/))

`scoop install kind`

## Create cluster with support for Ingres

`kind create cluster --config .\cluster.yaml`

## Deploy Ingress nginx controller

`kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml`

## Test ingres

### Deploy test resources

`kubectl apply -f ingres-test.yaml`

### Test deployed resource

```bash
# should output "foo-app"
curl localhost/foo/hostname

# should output "bar-app"
curl localhost/bar/hostname
```
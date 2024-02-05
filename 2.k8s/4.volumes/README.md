# Volumes

## Static Provisioning

```mermaid
flowchart LR
    A["&#128110; Admin"] --Creates--> PV[Persistent Volume]
    POD --Needs--> PVC[Persistent Volume Claim] --Search--> PV --Provides--> V[Volume]
    POD --Mounts--> V
```

## Dynamic Provisioning

```mermaid
flowchart LR
    A["&#128110; Admin"] --Defines--> SC[Storage Classes]
    POD --Needs--> PVC[Persistent Volume Claim] --Asks--> SC --Provides--> PV[Persistent Volume] --Provides--> V[Volume]
    POD --Mounts--> V
```

## Get resources

```bash
# Get storage classes
kubectl get storageclasses # or kubectl get sc

# Get persistent volumes
kubectl get persistentvolumes # or kubectl get pv

# Get persistent volume claims
kubectl get persistentvolumeclaims # or kubectl get pvc
```

## Configmap

### Get configmaps

`kubectl get configmap`

or

`kubectl get cm`

## Secret

### Get secrets

`kubectl get secrets`
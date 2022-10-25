# kubectl get
Using `kubectl get` commands, we can list down all the resources that are currently present. Also, using flags, we can filter the list accordingly.

## How to get all the resources in Kubernetes?
To get all the resources in all the namespaces.
`kubectl get all -A`

In the specific namespace.
`kubectl get all -n namespaceName`

## How to get any specific resources in Kubernetes?
`kubectl get resourceName -n namespaceName`

Example,
```
% kubectl get pod -n default
NAME     READY   STATUS    RESTARTS   AGE
server   1/1     Running   0          5d15h
```

## How to get pods with a selector flag?
Definition file for pod with selector field.
```

```
### Command
`kubectl get resourceName -n namespaceName -l selectorKey=selectorValue`

### Output

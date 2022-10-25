# kubectl create
Using `kubectl create` we can create all the the kubernetes resourses by passing the definition file of that resourse.

### Definition file format
```
apiVersion:
kind:
metadata:

spec:
```

## How to create a pod using `kubectl create` command with definition file?
### Definition file for pod
```
---
apiVersion: v1
kind: Pod
metadata:
  name: server
  labels:
    app: frontend
spec:
  containers:
  - name: nginxserver
    image: nginx:latest
```
### Command
`kubectl create -f definitionfile.yaml`

## kubectl create sub commands
### How to create a clusterrole using `kubectl create` command with verb get, apply on pod server?
### Imperitive way
`kubectl create clusterrole serverClusterRole --verb=get --resource=pods --resource-name=server`

### Declaritive way
#### Definition file
```
---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata:
  name: serverClusterRole
rules:
- apiGroups:
  - ""
  resourceNames:
  - server
  resources:
  - pods
  verbs:
  - get
```
#### Command
`kubectl create -f clusterRoleDefinition.yaml`


# k8s-deployment-sample
Complete webapp process with k8s and kustomization

## kubectl - How to?
* Replace the docker images on backend/frontend deployment files (you can either download from gcr or local)
* Run the following commands to spin up the pods and services:
```bash
$ kubectl apply -k k8s/
```
* Access your application through browser: `http://localhost:3000`

## Teardown
* You can delete the entire deployment and persistent volumes running the following command:
```bash
$ kubectl delete -k k8s/
```

## helm - How To?
* Replace the image name in the deployment files
* Run the following command to deploy the chart:
```bash
# postgres deployment
$ helm install -f postgres/database-postgres.yaml postgres ./postgres

# backend deployment
$ helm install -f backend/backend-api.yaml backend-api ./backend

# frontend deployment
$ helm install -f frontend/frontend-app.yaml frontend ./frontend
```
## TearDown
* You can delete and remove all deployments running the following command:
```bash
# 1. First list all deployments just to make sure you will remove the correct one:
$ helm list

# 2. Run helm uninstall passing the deployment name: e.g. postgres
$ helm uninstall postgres
```
# Local Environment
[Rancher Desktop](https://rancherdesktop.io/)
* k8s 1.24.4
* helm v3.9.1
* dockerd (moby)
* k9s v.0.26.3


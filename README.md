# k8s-deployment-sample
Complete webapp process with k8s and kustomization

# How to?
* Replace the docker images on backend/frontend deployment files (you can either download from gcr or local)
* Run the following commands to spin up the pods and services:
```bash
$ kubectl apply -k k8s/
```
* Access your application through browser: `http://localhost:3000`

# Teardown
* You can delete the entire deployment and persistent volumes running the following command:
```bash
$ kubectl delete -k k8s/
```

# Local Environment
[Rancher Desktop](https://rancherdesktop.io/)
* k8s 1.24.4
* dockerd (moby)
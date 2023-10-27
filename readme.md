nfs provisioner for kubernetes clusters.


Use Helm to install the provisioner:

```bash 
helm repo add nfs-subdir-external-provisioner https://kubernetes-sigs.github.io/nfs-subdir-external-provisioner/
helm upgrade --install  nfs-subdir-external-provisioner nfs-subdir-external-provisioner/nfs-subdir-external-provisioner --values values.yaml --create-namespace
```

Test it with test-deployment:

```sh
kubectl apply -f- test-deployment.yaml
```

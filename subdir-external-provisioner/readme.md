nfs provisioner for kubernetes clusters.


Use Helm to install the provisioner:

```bash 
helm repo add nfs-subdir-external-provisioner https://kubernetes-sigs.github.io/nfs-subdir-external-provisioner/
helm upgrade --install  nfs-subdir-external-provisioner nfs-subdir-external-provisioner/nfs-subdir-external-provisioner --values values.yaml --create-namespace
```

Test it with test-deployment:

apply
```sh
kubectl apply -f test-deployment.yaml
```

exec no container
```sh
kubectl  k exec -ti <pod name> -- sh
```

Verifique os discos montados
```sh 
df -h
Filesystem                Size      Used Available    Use%   Mounted on
10.88.20.71:/nfsserver    5.0G         0      5.0G    0%     /path/in/container
```

Para testar suas applicações utilize o storageclass: `nfs-braporto-local` em seus pvc 


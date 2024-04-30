# kubectl jsonpath

```shell
kubectl get clusterrolebindings.rbac.authorization.k8s.io -ojsonpath='{range .items[?(.subjects[].name == "system:serviceaccounts")]}{.metadata.name}{"\n"}'
```



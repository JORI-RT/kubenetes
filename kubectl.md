```sh
kubectl get .. list
kubectl describe ... 
kubectl logs ...
kubectl exec 
```

```sh
kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}'

```
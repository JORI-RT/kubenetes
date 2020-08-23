```sh
kubectl get .. 
kubectl describe ... 
kubectl logs ...
kubectl exec 
kubectl get event
```

```sh
kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}'

```
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


```sh
## ヒアドキュメントの使い方
#EOFまでをtestにリダイレクト 
cat <<EOF > test
line1
line2
line3
EOF
```
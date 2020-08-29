```sh
kubectl get .. 
kubectl describe ... 
kubectl logs ... -f , --since , --tail 
kubectl logs [Pod名] [Container名]
kubectl exec 
kubectl get event
kubectl config set-context --current --namespace=<insert-namespace-name-here>
k rollout restart deploy deploymentの名前
# manifestの構造
k explain pod.spec --recursive
# manifestの説明
k explain pod.spec

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
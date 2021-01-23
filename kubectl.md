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
k rollout restart deploy deployment名
kubectl get componentstatuses


# クラスターの切り替え
# ①コンテキストに設定されているクラスター一覧を取得
kubectl config get-clusters
# ②現在のクラスター確認
kubectl config current-context
# ③接続クラスター変更
kubectl config use-context [cluster name]
```

```sh
kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}'

```


```sh
## PODを一括でけす
k get pod | grep hoge | awd '{print $1}' | kubectl delete pod 
```
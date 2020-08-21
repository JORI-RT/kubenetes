# kubenetes

# Docker desktopで[minikubeチュートリアル](https://kubernetes.io/ja/docs/tasks/tools/install-minikube/)試す

## ch1
```sh
kubectl create deployment hello-node --image=k8s.gcr.io/echoserver:1.4
kubectl get deployments
kubectl get pods
# clusterの設定がみれる
kubectl config view
# deploymentをサービスとして外部に公開
kubectl expose deployment hello-node --type=LoadBalancer --port=8080

```

## ch2 
```sh
kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.10
# サービスとして公開
kubectl expose deployment hello-minikube --type=NodePort --port=8080
```
# 2 チュートリアル
```sh
# クラスターの情報をみる
k cluster-info
# クラスターのnodeを見る
k get node
# デプロイ
kubectl create deployment kubernetes-bootcamp --image=gcr.io/google-samples/kubernetes-bootcamp:v1
# kubenetesクラスター内のpodには外部からはアクセスできない、以下プロキシコマンドをかませば一時てきに公開できる
kubectl proxy
# ctl + c でproxyを終わらすとアクセスできない
curl http://localhost:8001/version

#### APIサーバはPODを作成したときデフォルトでendpointを作成する

```

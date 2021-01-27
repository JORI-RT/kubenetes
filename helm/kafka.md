## helm kafka
```sh
# helmをインストール
OS的にサポート外だったから、ソースからビルドする必要あり
## helmのリポジトリをaddする
helm repo add incubator https://charts.helm.sh/incubator
# kafkaのchartを探す
helm search repo kafka
-- result --
incubator/kafka          	0.21.5       	5.0.1      	DEPRECATED Apache Kafka is publish-subscribe me...
# chartをインストールする
helm install --name-template kafka-service incubator/kafka
---  result --- 
NAME                        READY   STATUS    RESTARTS   AGE
kafka-service-0             1/1     Running   1          59m
kafka-service-1             1/1     Running   0          57m
kafka-service-2             1/1     Running   0          56m
kafka-service-zookeeper-0   1/1     Running   0          59m
kafka-service-zookeeper-1   1/1     Running   0          58m
kafka-service-zookeeper-2   1/1     Running   0          57m
## これでkafkaクラスターができた
## 次にTOPICを作成
# まず、コマンド実行用のコンテナを建てる
k run -it kafka --iamge=solsson/kafka:0.11.0.0 /bin/bash
# 以降、kafkaコンテナ内での作業
# TOPICを作成
./bin/kafka-topics.sh --create --zookeeper kafka-service-zookeeper:2181 --replication-factor 3 --partitions 10 --topic photos-1
# zookeeperのログを見ると、作成の様子を確認できる
# 以下でTOPICにメッセージを送信できるコンソールがひらく、適当にメッセージを送信
./bin/kafka-console-producer.sh --broker-list kafka-service:9092 --topic photos-1
# stern等でログを確認できる
stern kafka-service
# 以下でTOPICからメッセージをPULLできる
./bin/kafka-console-consumer.sh --bootstrap-server kafka-service:9092 --from-beginning --topic photos-
# stern等でログを確認できる
stern kafka-service
```

## LINK
[helmの公式サイト](https://helm.sh/docs/intro/quickstart/)
[helmのinbubatorのURL](https://helm.sh/blog/new-location-stable-incubator-charts/)

## 所管、やること
helmをもう少しほってみる
kafkaのアーキテクチャを理解する
->TOPICから２つのCONSUMERでメッセージをPULLしたらどうなるか
zookeeperとkafka-servcieの関係
helmがdepricatedだらけだったのが気になる
ちょっとしたツールならbashで作れそう
ー＞ちょっとしたツールをメッセージングが必要な場面は思い浮かばないが、、、
## Deployment
podの管理　ー＞　PODを監視して理想状態へもっていく役割

## Service
通常PODにはクラスタ内部のIPからしかアクセスできない
PODを外部に公開するために必要
selectorでServiceとなるPODを割り当てる

## POD
論理的なホスト
IPアドレスとポートを共有する

## NODE
マスターによって管理される
複数のPODを持てる
kubeletとコンテナランタイムをもつ

## LabelSelector
Serviceの対象となるPODのセットをけてtする

## replicaSetとは`


## Volumeとは
Dockerより厳密に管理されたもの？
### pod.spec.volumes.emptyDir
PODがNODEに割り当てられたとき、作成される
おそらくPOD同士で共有はできない
# [Pod to Pod Networking](https://kubernetes.io/docs/concepts/cluster-administration/networking/)
## 概要
それぞれのPODはIPアドレスを持つ
すべてのNODE上のPODはNATなしでPOD感通信ができる（この意味とは、当たり前にきこえる）
Kubeletや、daemonはあるノード上の全てのPODに通信できる
POD内のコンテナはIPを共有する、つまりlocalhostでPOD内のコンテナは通信できる

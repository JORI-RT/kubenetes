# [Kubernetesのプラグイン機構](https://techblog.yahoo.co.jp/entry/2020081830014718/)
* 任意のサブコマンドを作成できる
* PATHに-区切りで実行ファイルがあればよい
  * kubectl-piyo ... kubectl piyoで実行可能
  * kubectl-piyo-poyo ... kubectl piyo poyoで実行可能
  * kubectl-piyo_bar ... kubectl piyo-barで実行できる

```sh
# プラグインの作成
echo -e '#!/bin/bash\n\necho "My first command-line argument was $1"' > kubectl-foo
chmod +x ./kubectl-foo

# プラグインのインストール
echo $PATH
/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
mv ./kubectl-foo /usr/local/bin

# プラグインの実行
kubectl foo hello
My first command-line argument was hello

```
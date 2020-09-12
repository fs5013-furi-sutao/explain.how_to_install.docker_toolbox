# Docker Toolbox 
レガシーな Windows 向けの Docker マネージメントツール、Docker Toolbox について説明する。
ここでは、Docker Toolbox で docker-compose ファイルを使ってコンテナを起動するところまで確認する。

## Docker Toolbox とは 

## VirtualBox のインストール
VirtualBox がまだインストールされていない場合は、Chocolatey で VirtualBox をインストールする。

インストールするには、管理者で開いた PowerShell で以下のコマンドを実行する。

```console
choco install virtualbox
```

## Docker 類のインストール
Docker Toolbox を使うには、以下の 3 つのモジュールが必要になる。
- docker
- docker-machine
- docker-compose

今回はこれらを scoop でインストールする。


すでに Scoop を導入している場合は、以下のコマンドで Docker の3つのモジュールを一度にインストールができる。

```console
scoop install docker docker-machine docker-compose
```

これらのモジュールを Scoop でインストールすると、Docker Toolbox の GUI である Kitematic が同時にインストールされる。

## Kitematic の起動
インストールされた Kitematic を起動する。

![Kitematic の初回起動](./kitematic_first_run.png) 

## Docker Toolbox でのコンテナ構造
レガシーな（2004 より前のバージョン）Windows 10 では、Docker Toolbox を使う。

通常の Linux 向けの Docker と違い、Docker Toolbox は VirtualBox で作った default という初期 Virtual Machine の上に Docker コンテナを構築する。

そのため、Docker コンテナへ接続できる IP アドレスも、この default VM の IP アドレスになる。

## default VM の IP アドレスの確認方法
default VM の IP アドレスを確認するには、VirtualBox を立ち上げる。

以下の VirtualBox のホーム画面を見て分かる通り、Kitematic の初回起動により、default という VM が作成・実行されていることが分かる。

![VirtualBox のホーム画面](./virtualbox_home.png)

この default をダブルクリックすることで、default VM のコンソール画面が表示される。コンソールに、以下のコマンドを実行し、IP アドレスの情報を表示させる。

```console
ifconfig
```

以下の場合、default VM の IP アドレスが `192.168.99.100` であることが分かる。

![VirtualBox の default VM のコンソール画面](./virtualbox_default_vm_console.png)

また、このようなネットワーク情報は、以下のコマンドで PowerShell などで見ることもできる。

```console
VBoxManage guestproperty enumerate "default" | findstr IP
```

## Docker コンテナを起動してみる







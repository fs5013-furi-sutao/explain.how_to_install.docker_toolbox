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

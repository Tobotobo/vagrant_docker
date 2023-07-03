# vagrant_docker

## 概要
Vagrant で Docker 環境を構築する。

## Vagrant (ベイグラント) とは
構成ファイル(Vagrantfile)を基に、仮想環境の構築から設定までを自動で行うことができるツール。  
VirtualBox など何れかの仮想化ソフトウェアがインストールされていることが前提。  
指定した仮想化ソフトウェア上に構築する。

## 前提
以下がインストールされていること

- Vagrant
- VirtualBox　※仮想化ソフトウェアが無い場合  

インストールする場合は winget が手軽でオススメ
```
winget install Oracle.VirtualBox
winget install Hashicorp.Vagrant
```

## 実行
- 本フォルダ上で ```vagrant up``` を実行
- 処理が終わったら ```vagrant ssh``` を実行  
  ※パスワードは vagrant
- ```docker --version``` で Docker のバージョンが表示されることを確認
- ```docker-compose --version``` で Docker Compose のバージョンが表示されることを確認
- ```cd /vagrant/nginx_example``` で nginx_example へ移動
- ```docker-compose up``` で nginx 実行
- ブラウザから http://192.168.33.10:8080/ にアクセスし Welcome to nginx! と表示されることを確認

## メモ
- 仮想環境の IP アドレスやメモリ容量の設定を変更したい場合は Vagrantfile を変更する
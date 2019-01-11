# Docker container内のFOSSologyからhost OS上のPostgreSQLにアクセスする方法

FOSSology は、ソースコードをスキャンしてオープンソースソフトウェア (OSS) のライセンスや著作権などの情報を検出するソフトウェアであり、OSS ライセンスのコンプライアンス遵守に大変有効なツールである。FOSSology には、(1) Dockerを使う (2) Vagrant と VirtualBox を使う (3) ソースコードからインストールする、の３つのインストール方法がある。(https://www.fossology.org/get-started/)

本文書で取り扱うのは (1)のDocker を使う方法であるが、Docker image 単体ではスキャンした結果の保存が保証されないため、データベースをコンテナの外部に用意することが推奨されている。そこで、Docker container 上の FOSSology から host OS 上の PostgreSQL データベースにアクセスする方法を紹介する。この文書が、FOSSologyを使ってみたい方々の手助けになることを希望する。

## 目次
1. 動作環境
2. Docker CE のインストール
3. FOSSology を動かしてみる
4. PostgreSQLのインストールとデータベース作成
5. FOSSology からhost OS上のPostgreSQLにアクセスする


## 1. テスト環境
ここに記載の内容は、以下の環境で動作テストした。

|Item |Description |
|--- | --- |
|Host OS |Debian 9 (Stretch)|
|Network |Broadband access to the Internet|
|CPU |Intel(R) Core(TM) i3-3220T CPU @ 2.80GHz|
|RAM |4GB|

## 2. Docker CE のインストール
Host OS である Debian に Docker CE をインストールする。以下のサイトの手順に従うが、apt-get コマンドは apt コマンドに置き換えることが推奨される。  
https://docs.docker.com/install/linux/docker-ce/debian/  
ここではコマンドのみを列挙するので、詳細は上記サイトを参照すること。

```
$ sudo apt remove docker docker-engine docker.io
$ sudo apt update
$ sudo apt install apt-transport-https ca-certificates curl gnupg2 software-properties-common
$ curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
$ sudo apt-key fingerprint 0EBFCD88
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
$ sudo apt update
$ sudo apt install docker-ce
```
一般ユーザの権限で Docker を起動できるように、ユーザ名を docker グループに追加する。この設定を反映させるには、コマンドの実行後、一旦ログアウトが必要なようである。

```
$ sudo gpasswd -a ${USER} docker
```
Hello-world イメージを実行してみて、Docker が正しくインストールされたことを確認する。

```
$ docker run hello-world
```
## 3. FOSSology を動かしてみる

以下のコマンドにより、あらかじめビルドされた FOSSology の Docker image を起動することができる。初回には、イメージを Dockerhub からダウンロードするので、いくらか時間がかかる。

```
$ docker run -p 8081:80 fossology/fossology
```
Webブラウザから http://IP_OF_DOCKER_HOST:8081/repo/ にアクセスして FOSSology のログイン画面を確認する。デフォルトのユーザ名/パスワードは、fossy/fossy である。  
参考URL：https://hub.docker.com/r/fossology/fossology/

ここまでの手順では FOSSology はコンテナ内部のデータベースを使用しており、スキャンした結果の保持は保証されない。そこで、次項以降で、外部データベースを使用するための設定を行う。

ここでは、docker ps コマンドで現在実行中のFOSSologyのContainer IDを調べ、docker stop コマンドでコンテナを停止する。

```
$ docker ps
CONTAINER ID        IMAGE                 COMMAND                  CREATED             STATUS              PORTS               NAMES
4a05838bafc4        fossology/fossology   "/fossology/docker-e…"   20 seconds ago      Up 18 seconds                           romantic_wu
$ docker stop 4a05838bafc4
```
## 4. PostgreSQLのインストールとデータベース作成

### 4.1 PostgreSQLのインストール

ホストOSにPostgreSQLをインストールする。

```
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install postgresql
```
### 4.2 ホストOS上で postgres ユーザのパスワードを設定

ホストOS上でpostgresユーザのパスワードを設定する。パスワードは任意である。

```
$ sudo passwd postgres
```

### 4.3 データベースの作成
上記で設定したパスワードで "postgres" としてログインし、データベース "fossology" を作成する。続けて、データベースのユーザ "fossy" を作成する。パスワードは "fossy" を設定する。

```
$ su - postgres
$ createdb fossology
$ createuser --pwprompt --interactive fossy
Enter password for new role: # Enter fossy here.
Enter it again: # Enter fossy here.
Shall the new role be a superuser? (y/n) n
Shall the new role be allowed to create databases? (y/n) n
Shall the new role be allowed to create more new roles? (y/n) n
```
## 5. FOSSologyからhost OS上のPostgreSQLにアクセスする

以下のコマンドでFOSSologyを起動する。今回は "-p 8081:80" は不要である。(付けても無視される)

```
$ docker run --network="host" -e FOSSOLOGY_DB_HOST="127.0.0.1" fossology/fossology
```
Webブラウザから http://IP_OF_DOCKER_HOST/repo/ にアクセスする。


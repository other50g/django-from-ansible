# 概要
DockerでAnsibleのHostとSlaveを構築し、HostからSlaveに対して以下のソフトをインストールする
* Nginx
* PostgreSQL
* gunicorn
* django

## Docker + ansible
* [【Ansible】DockerでAnsibleハンズオン \- Qiita](https://qiita.com/Naoto9282/items/39eeefa5de652b857372)
* [Naoto92X82V99/docker\-ansible: Dockerを使って、Ansibleにハンズオン](https://github.com/Naoto92X82V99/docker-ansible)

### 実行方法
```shell
# コンテナーにログイン
$ docker-compose exec ansible bash
$ ansible-playbook -i inventry.ini playbook.yml
```

## ansible + nginx
* [Ansibleを使ってnginxをインストールする \- Qiita](https://qiita.com/takakuda/items/12d4fa568f71c8e20cef)
* [Full Example Configuration \| NGINX](https://www.nginx.com/resources/wiki/start/topics/examples/full/)
* [CentOS、RHEL、または Amazon Linux を実行している EC2 インスタンスの EPEL リポジトリを有効にする](https://aws.amazon.com/jp/premiumsupport/knowledge-center/ec2-enable-epel/)
* [Docker上のAmazonLinux2でLaravelの環境構築 \- Qiita](https://qiita.com/skyknsk/items/c9710bb952a854a32cfd)
* [CentOS7のコンテナでsystemctlを使うための方法 \- Qiita](https://qiita.com/Targityen/items/6e80b855b79d521412f0)
* [Docker compose \+ CentOS7でFailed to get D\-Bus connection: Operation not permittedが出た場合の対処法 \- Qiita](https://qiita.com/TsukasaGR/items/26b01ca5bd68c2aec251)

### 苦労したところ
Amazon Linuxを利用しているため、`systemctl`が実行できない`Failed to get D-Bus connection: Operation not permitted`となった。
docker-compose.ymlに`command: /sbin/init`と記述することによって対応。


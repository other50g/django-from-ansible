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

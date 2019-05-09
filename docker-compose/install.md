# 目標
開発環境をdocker-composeを使って作成する。  
下記を入れる。(随時更新)  
 - gitlab
 - jenkins
 - ・・・

# 初期設定
もろもろやっておく  
`yum -y update`もすること  


# install
dockerのインストール
```
yum install -y yum-utils device-mapper-persistent-data lvm2

yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

yum makecache fast

yum install -y docker

systemctl start docker

systemctl enable docker
```
確認
```
docker ps
```

docker-composeのインストール
```
curl -L https://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose

chmod +x /usr/local/bin/docker-compose

docker-compose --version

curl -L https://raw.githubusercontent.com/docker/compose/$(docker-compose --version | awk 'NR==1{print $NF}')/contrib/completion/bash/docker-compose > /etc/bash_completion.d/docker-compose
```

gitlabのインストール
[参考](https://github.com/sameersbn/docker-gitlab#quick-start)

```
yum -y install wget

cd 
pwd

wget https://raw.githubusercontent.com/sameersbn/docker-gitlab/master/docker-compose.yml

```
docker-compose.ymlを編集  


jenkinsのインストール  
```
mkdir -p /srv/docker/jenkins/jenkins
chmod -R 1000 /srv/docker/jenkins/jenkins

```
docker-compose.ymlを編集

# 起動
必要なコンテナすべて書ききったら以下で起動する。  
※以下のコマンドは標準出力にログが垂れ流しになるが初回は見といたほうがいい。
```
docker-compose up
```


# 接続できるか確認  
 - gitlab  
http://IPaddress:10080  

 - jenkins  
http://IPaddress:18080  
jenkinsの初回ログイン時のパスワードは以下コマンドでコンテナに入って確認する。  
```
docker exec -it docker_jenkins_1 bash
```

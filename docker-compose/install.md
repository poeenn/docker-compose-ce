# �ڕW
�J������docker-compose���g���č쐬����B  
���L������B(�����X�V)  
 - gitlab
 - jenkins
 - �E�E�E

# �����ݒ�
����������Ă���  
`yum -y update`�����邱��  


# install
docker�̃C���X�g�[��
```
yum install -y yum-utils device-mapper-persistent-data lvm2

yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

yum makecache fast

yum install -y docker

systemctl start docker

systemctl enable docker
```
�m�F
```
docker ps
```

docker-compose�̃C���X�g�[��
```
curl -L https://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose

chmod +x /usr/local/bin/docker-compose

docker-compose --version

curl -L https://raw.githubusercontent.com/docker/compose/$(docker-compose --version | awk 'NR==1{print $NF}')/contrib/completion/bash/docker-compose > /etc/bash_completion.d/docker-compose
```

gitlab�̃C���X�g�[��
[�Q�l](https://github.com/sameersbn/docker-gitlab#quick-start)

```
yum -y install wget

cd 
pwd

wget https://raw.githubusercontent.com/sameersbn/docker-gitlab/master/docker-compose.yml

```
docker-compose.yml��ҏW  


jenkins�̃C���X�g�[��  
```
mkdir -p /srv/docker/jenkins/jenkins
chmod -R 1000 /srv/docker/jenkins/jenkins

```
docker-compose.yml��ҏW

# �N��
�K�v�ȃR���e�i���ׂď�����������ȉ��ŋN������B  
���ȉ��̃R�}���h�͕W���o�͂Ƀ��O�����ꗬ���ɂȂ邪����͌��Ƃ����ق��������B
```
docker-compose up
```


# �ڑ��ł��邩�m�F  
 - gitlab  
http://IPaddress:10080  

 - jenkins  
http://IPaddress:18080  
jenkins�̏��񃍃O�C�����̃p�X���[�h�͈ȉ��R�}���h�ŃR���e�i�ɓ����Ċm�F����B  
```
docker exec -it docker_jenkins_1 bash
```

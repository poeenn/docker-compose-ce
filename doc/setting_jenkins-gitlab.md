# jenkins　gitlab
jenkinsとgitlabの連携設定をする。とりあえず以下を参照。  
https://qiita.com/takamii228/items/3598f403518c296f93f3  

# 注意
docker-composeで実行しているので、jenkins-gitlab間はdocker間通信になる。  
なので、jenkinsからgitlabは`http://gitlab`で接続する。  
※docker-compose.yml内のlinksで指定した値がホスト名

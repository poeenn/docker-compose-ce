# docker-compose-ce
開発環境の構築でdockerを使用する。  
理由は以下  
 - そのまま入れると移行するときに面倒(Kubernetesに移行するかもな要件がある)
 - サーバのOSが不明なのでWindowsでもVirtualBox入れて作れるようにするため。
 - 構築が楽

複数のdockerを連携するときはdocker-composeを使うのが一般的っぽいので使う。  
（そもそもgitlabの公式で推奨されている）  

# gitlab
ソース管理としてgitを使うが、そのままでは使いづらいのでクライアントソフトとしてgitlabを使用する。  
(実際に使うのはEclipse上でかもしれないが・・・)  
おじさんとも連携できる。  


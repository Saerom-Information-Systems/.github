## 선행조건
- [docker 설치](./initial_docker.md)

# onlyoffice 설치
### docker 설치후 2606 포트로 실행
### ⚠️ 주의사항
**secret key는 반드시 "XXb8SYW2pMHKMHvtvgUDrpTrcNcXVItJ"로 고정 선언해야 합니다.**  
선언하지 않으면 재시작 시마다 키가 변경되어 연동이 끊어집니다.
``` bash
sudo docker run -i -t -d -p 2606:80 --restart=always \
    --name onlyoffice-server \
    -v /app/onlyoffice/DocumentServer/logs:/var/log/onlyoffice  \
    -v /app/onlyoffice/DocumentServer/data:/var/www/onlyoffice/Data  \
    -v /app/onlyoffice/DocumentServer/lib:/var/lib/onlyoffice \
    -v /app/onlyoffice/DocumentServer/db:/var/lib/postgresql \
    -e JWT_SECRET=XXb8SYW2pMHKMHvtvgUDrpTrcNcXVItJ \
    onlyoffice/documentserver-de:7.5.0
```

2. hosts 파일 등록
```bash
sudo docker exec onlyoffice-server /bin/bash -c "echo '${appl Server IP} ${appl Server Host}' >> /etc/hosts"
```
ex) 
```bash
sudo docker exec onlyoffice-server /bin/bash -c "echo '192.168.1.100 example.com' >> /etc/hosts"
```

# 공동편집 WAS 실행
1. [ematenapi](https://github.com/Saerom-Information-Systems/ematenapi)를 cline
2. root의 config와 task/coedit/config를 해당 서버에 맞춰 설정
3. root의 app.was.coedit.js를 실행

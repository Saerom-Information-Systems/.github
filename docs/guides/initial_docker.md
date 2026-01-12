# docker 설치
### 1. docker 설치 명령어
```bash
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

### 2. notes에 docker 실행 권한 부여
sudo usermod -aG docker notes

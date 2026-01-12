## 선행조건
- [docker 설치](./initial_docker.md)


# Jenkins 설치

### docker에 jenkins image 다운로드 및 jenkins container 실행
```bash
docker run -d --name jenkins-server -p {사용할 PORT}:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home  jenkins/jenkins:latest
```
### ex) 9080 포트로 수행
```bash
docker run -d --name jenkins-server -p 9080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home  jenkins/jenkins:latest
```

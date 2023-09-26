# Streamlit app Docker Image

## 1. Login with your AWS console and launch an EC2 instance
## 2. Run the following commands

Note: Do the port mapping to this port:- 8501

```bash
sudo apt-get update -y # 패키지 목록 업데이트

sudo apt-get upgrade # 설치된 패키지를 최신 버전으로 업그레이드

#Install Docker

curl -fsSL https://get.docker.com -o get-docker.sh 

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu # ubuntu 사용자를 docker 그룹에 추가

newgrp docker # 새로운 그룹 설정을 적용
```

```bash
git clone "your-project" # 프로젝트를 복제
```

```bash
docker build -t entbappy/stapp:latest .  # 현재 디렉터리의 Dockerfile을 사용하여 이미지 빌드
```

```bash
docker images -a  # 모든 도커 이미지를 리스트업
```

```bash
docker run -d -p 8501:8501 entbappy/stapp # 이미지를 실행하여 컨테이너 생성, 포트 8501로 매핑
```

```bash
docker ps  # 실행 중인 컨테이너 리스트업
```

```bash
docker stop container_id # 특정 컨테이너를 중지
```

```bash
docker rm $(docker ps -a -q) # 모든 중지된 컨테이너를 삭제
```

```bash
docker login # 도커 허브에 로그인
```

```bash
docker push entbappy/stapp:latest # 이미지를 도커 허브에 푸시
```

```bash
docker rmi entbappy/stapp:latest # 로컬에서 특정 이미지 삭제
```

```bash
docker pull entbappy/stapp # 도커 이미지를 도커 허브에서 로컬로 다운로드
```







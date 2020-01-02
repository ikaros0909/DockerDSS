# Docker Desktop
## Docker Desktop 설치
다운로드 : https://www.docker.com/products/docker-desktop  
Docker: “no matching manifest for windows/amd64 in the manifest list entries”  
Right click Docker instance  
Go to Settings  
Daemon  
Advanced  
Set the "experimental": true  
Restart Docker  

# Docker
## Docker 빌드
docker build --tag jinhak-node:DSS2021 .  

## Docker 실행
- 단일실행  
docker run --name jinhak-node-DSS2021-0 -p 3000:80 jinhak-node:DSS2021  

- 멀티실행  
docker run -d --name jinhak-node-DSS2021-0 -p 3001:3000 jinhak-node:DSS2021  
docker run -d --name jinhak-node-DSS2021-1 -p 3002:3000 jinhak-node:DSS2021  
docker run -d --name jinhak-node-DSS2021-2 -p 3003:3000 jinhak-node:DSS2021  

## Docker 프로세스 확인
- docker container 확인  
docker ps  

- docker image 확인  
docker images  

## Docker 경로 확인 및 접근
docker exec nginx-server ls  
docker exec -i -t nginx-server /etc  
docker exec -i -t  nginx-server /bin/bash  

## Docker 종료
- docker container 중지 및 삭제  
docker stop nginx-server  
docker rm nginx-server  

- 현재 실행되고 있는 모든 docker container 삭제  
docker rm -f $(docker ps -a -q)  

- docker image 삭제  
docker rmi [image id]  

# NginX
## NginX 설치
docker pull nginx  

## NginX Docker 빌드
cd nginx
docker build --tag jinhak-nginx:DSS2021 .  

## NginX 실행  
docker run -d --name nginx-server -p 2021:3000 jinhak-nginx:DSS2021  

# Docker-Compose  
## Docker-Compose  
docker-compose build # 새로운 변경사항을 반영  
docker-compose up # 서비스 실행  

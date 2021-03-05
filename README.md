# Docker 명령어 정리

### Docker version 확인

```
C:\>docker version
Client: Docker Engine - Community
 Cloud integration: 1.0.7
 Version:           20.10.2
 API version:       1.41
 Go version:        go1.13.15
 Git commit:        2291f61
 Built:             Mon Dec 28 16:14:16 2020
 OS/Arch:           windows/amd64
 Context:           default
 Experimental:      true

Server: Docker Engine - Community
 Engine:
  Version:          20.10.2
  API version:      1.41 (minimum version 1.12)
  Go version:       go1.13.15
  Git commit:       8891c58
  Built:            Mon Dec 28 16:15:28 2020
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          1.4.3
  GitCommit:        269548fa27e0089a8b8278fc4fc781d7f65a939b
 runc:
  Version:          1.0.0-rc92
  GitCommit:        ff819c7e9184c13b7c2607fe6c30ae19403a7aff
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0

```



### Docker Image 확인

```
C:\>docker images
REPOSITORY     TAG       IMAGE ID       CREATED        SIZE
centos-nginx   2         ae9fdea7209b   3 hours ago    357MB
centos-nginx   1         568e6da0b7c7   5 hours ago    290MB
centos         latest    300e315adb2f   2 months ago   209MB

```



### Docker Image 삭제

```
## 도커이미지 삭제
C:\docker rmi nginx:latest   ## nginx(이미지명):latest(태그)

## 사용하지 않는 도커 이미지 일괄 삭제
C:\docker rmi $(docker images -f "dangling=true" -q)
```



### Docker Image Build

```
C:\docker build -t iamge:tag .
## -t, --tag : 이미지명 태그명 설정
## image : 이미지 명
## tag : 태그명
## . : 현재 디렉토리 기준. Dockerfile을 읽어서 빌드함.
```



### Docker Container 실행

```
docker
```



### Docker Container 확인

```
C:\docker ps		## 활성화된 도커 컨테이너
C:\docker ps -a		## 모든 도커 컨데이너
```



### Docker Container 삭제

```
C:\docker rm [container_name]			## 해당 컨테이너 삭제. 컨테이너 ID로 삭제 가능(ID는 다 입력하지 않아도 됨)
C:\docker rm -f [container_name]		## 해당 컨테이너 강제 삭제. 
C:\docker rm $(docker ps -a -q)			## 일괄삭제
```



### Docker log 확인

```
C:\docker logs [contaienr_name] 
```



### Docker Container 내부 bash 접속

```
C:\docker exec -it [container_name] bash
## -i : 표준입력 활성화
## -t : TTY 모드. 통상 -it 사용
## [container_name] : 컨테이너명
## bash : 사용할 쉘
```


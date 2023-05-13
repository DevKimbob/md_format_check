<p float="left">
    <img src="Images/PIN.png" alt="PINLAB" height="100">
    <img src="Images/docker.png" alt="docker" height="100">
</p>

# K8s Perfect Guide

**Table of Contents**
* [1. Docker](#1-docker)


# 1. Docker
docker image를 생성할 때 주의할 점
1. 1컨테이너당 1프로세스
2. 변경불가 인프라 & 경량 이미지 (경량 기반이미지, apt 캐시파일 삭제, 레이어 줄이기, squash)
3. 실행은 root 이외의 사용자 (Dockerfile : USER 검색)

Dockerfile 명령어
* LABEL : 메타데이터를 K:V 형식으로 지정
* USER / WORKDIR : 실행 계정 / 디렉터리(없을 시 생성)
* EXPOSE : Listen할 포트 지정
* RUN : build 시 실행 명령어
* ADD / COPY
  * COPY : 단순 복사
  * ADD : tar.gz 압축해제 후 복사
* ENTRYPOINT / CMD : container 실행 시, `$ENTRYPOINT $CMD`가 실행된다고 생각
  * ENTRYPOINT : 실행 명령어
  * CMD : 실행 명령어 인수

Dockerfile -> Docker image build  
```docker image build -t <REPOSITORY>:<TAG> <dockerfile_dir>```
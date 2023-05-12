<img src="Images/PIN.png" alt="PINLAB" height="100">
<img src="Images/docker.png" alt="docker" height="100" padding-left="100px">

K8s Perfect Guide
===

**Table of Contents**
* [1. Docker](#1-docker)



# 1. Docker
docker image를 생성할 때 주의할 점
1. 1컨테이너당 1프로세스
2. 변경불가 인프라 & 경량 이미지 (경량 기반이미지, apt 캐시파일 삭제, 레이어 줄이기, squash)
3. 실행은 root 이외의 사용자 (Dockerfile : USER 검색)

* RUN : build 시
* ENTRYPOINT / CMD : container 실행 시, $ENTRYPOINT $CMD가 실행된다고 생각


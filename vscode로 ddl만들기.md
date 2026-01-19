ddl파일에 사용자 정보 추가 및 수정

데이터 폴더의 파일들 삭제

정보 추가 docker compose up -d
정보 삭제 docker compose down

정보 추가 후-도커 환경으로 접속
mariaDB 접속 : docker exec -it mariadb /bin/bash

root: 리눅스 환경

whoami 

cd samples

ls -l

mariadb -u root -p edu

password = 컴포즈 파일의 페스워드

show tables ;

셈플즈폴더 - 덤프 파일 내용을 한 줄씩 실행

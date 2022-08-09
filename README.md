# DockerTutorial

> <h2>이미지 관련 명령어</h2>
> 이미지 검색 : docker search [옵션] <이미지이름:태그명>   </br>
> 이미지 다운로드 : docker pull [옵션] <이미지이름:태그명>   </br>
> 이미지 목록 출력 : docker images   </br>
> 이미지 상세보기 docker inspect [옵션] <이미지이름:태그명>   </br>
> 이미지 삭제 : docker rmi [옵션] <이미지이름>   </br>

> <h2>컨테이너 관련 명령어</h2>
> 컨테이너 생성 : docker create [옵션] <이미지이름:태그명>   </br>
> 컨테이너 실행 : docker start [옵션] 컨테이너이름   </br>
> 컨테이너 생성/실행 : docker run [옵션] <이미지이름:태그명>   </br>
> pull -> create -> start = run   </br>
> 컨테이너 목록 확인 : docker ps      </br>
> 컨테이너 중지 : docker stop [옵션] 컨테이너이름   </br>
> 컨테이너 삭제 : docker rm [옵션] 컨테이너이름   </br>
> 포그라운드로 실행중인 컨테이너 연결 : docker attach [옵션] 컨테이너이름   </br>
> 동작중인 컨테이너에 NEW 명령어 추가 실행 : docker exec [옵션] 컨테이너이름   </br>
> ex)$ docker exec -it 컨테이너이름 /bin/bash   </br>
> 컨테이너에서 동작되는 프로세스 확인 : docker top [옵션] 컨테이너이름   </br>
> 컨테이너가 생성한 로그 보기 : docker logs [옵션] 컨테이너이름   </br>

> <h2>컨테이너 리소스 확인</h2>
> cAdvisor를 통해 확인 가능</br>

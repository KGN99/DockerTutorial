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
> 컨테이너 리소스 확인 : docker stat</br>
> 컨테이너 이벤트 확인 : docker event</br>

> <h2>컨테이너 리소스 제한</h2>
> <h3>MEMORY 리소스 제한</h3>
> 최대 메모리 양 : -m,-memory</br>
> $ dcoker run -d -m 512m <이미지,컨테이너></br>
> 스왑 메모리 영역 설정(메모리+스왑, 생략시 메모리의 2배) : --memory-swap</br>
> $ dcoker run -d -m 200m --memory-swap 300m <이미지,컨테이너></br>
> 소프트 제한 값 설정 : --memory-reservation</br>
> $ dcoker run -d -m 1g --memory-reservation 500m <이미지,컨테이너></br>
> OOM Killer 설정 : --oom-kill-disable</br>
> $ dcoker run -d -m 200m --oom-kill-disable=true <이미지,컨테이너></br>
> <h3>CPU 리소스 제한</h3>
> CPU core 수 지정 : --cpus</br>
> $ docker run -d --cpus 0.5 <이미지,컨테이너></br>
> CPU 코어 할당(index 0부터) : --cpuset-cpus</br>
> $ docker run -d --cpuset-cpus 0-3 <이미지,컨테이너></br>
> CPU 비중 설정(기본 1024) : --cpu-share</br>
> $ docker run -d --cpu-share 2048 <이미지,컨테이너></br>
> <h3>Block I/O 제한<h3>

> <h2>컨테이너 스토리지</h2>
> Volume Mount : -v <host path>:<containter mount path>:<read write mode></br>
> $ docker run -d -v /dbdata:/var/lib/mysql:ro</br>
> 볼륨 리스트 확인 : docker volume ls</br>

> <h2>컨테이너 네트워크</h2>
> <h3>포트 포워딩</h3>
> 컨테이너 포트를 외부로 노출시켜 외부 연결 허용</br>
> ip tables rule을 통한 포트 노출 : -p </br><hostPost>:<containerPost></br>
> <h3>네트워크 추가</h3>
> $ docker network create --driver bridge --subnet <서브넷 주소> --gateway <게이트웨이 주소> <네트워크명></br>
> $ docker network create --driver bridge --subnet 192.168.100.0/24 --gateway 192.168.100.254 mynet</br>
> 네트워크 지정 : docker run -d --net <네트워크명> --ip <아이피 주소> -p <포트포워딩></br>
> <h3>컨테이너 간 통신</h3>
> $ docker run -d --link <컨테이너명>:<호칭명> [포트포워딩]</br>

> <h3>도커 컴포즈</h3>
> version : 컴포즈 버전 (버전에 따라 지원 문법이 다르다.)</br>
> services : 컨테이너 옵션을 정의하는 공간</br>
> build : 컨테이너 빌드</br>
> image : 컴포즈를 통해 실행할 이미지 지정</br>
> command : 컨테이너에서 실행될 명령어 지정</br>
> port : 컨테이너가 공개하는 포트 나열</br>
> link : 다른 컨테이너와 연계할 때 연계할 컨테이너 지정</br>
> expose : 포트를 링크로 연계된 컨테이너에게만 공개할 포트</br>
> volumes : 컨테이너에 볼륨을 마운트</br>
> environment : 환경변수 지정</br>
> restart : 컨테이너가 종료될 때 적용할 restart 정책 no(재시작 되지 않음), always(수동으로 끄기전까지 항상 재시작), on-failure(오류가 있을 시 재시작)</br>
> depends_on : 컨테이너 간 종속성을 정의, 정의한 컨테이너가 먼저 동작되어야 한다</br>
> <a href="https://velog.io/@gmtmoney2357/Docker-%EC%BB%B4%ED%8F%AC%EC%A6%88compose">docker-compose 명령어</a>

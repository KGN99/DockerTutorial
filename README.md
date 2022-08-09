# DockerTutorial

컨테이너 만들어보기   
$ docker build -t webserver:v1 ./webserver   
$ docker run -d -p 80:80 --name web webserer:v1 .   
![image](https://user-images.githubusercontent.com/110814485/183546947-6e86587e-e2ee-4124-9034-937e6c45a3e8.png)   
$ docker build -t hellojs ./hellojs   
$ docker run -d -p 8080:8080 --name hellojs hellojs:latest   
![image](https://user-images.githubusercontent.com/110814485/183547205-4db89874-3fab-4bfd-80de-480f3ac6f52a.png)   


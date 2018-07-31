# Docker sample

## Command  
```yml
docker-compose.yml

version: '3'
services:
  jenkins-server:
    image: jenkins
    ports: 
      - "8080:8080"
      - "50000:50000"
    volumes:
      - ../../jenkins-home:/var/jenkins_home/
```  
```Dockerfile
Dockerfile

FROM jenkins/jenkins:lts

ADD ngrok-stable-linux-amd64.zip /
```  
```Makefile
Makefile

build:
	docker build -t jenkins .
	docker-compose up -d
	docker exec -it -u root jenkins-with-docker_jenkins-server_1 /bin/bash
```  
Code is simple, first.
```
make build
```
This will build images and up the container. After that, you should unzip the ngrok zip file and start ngrok.
```
unzip ngrok-stable-linux-amd64.zip
./ngrok http 8080
```
Done. Terminal will show you the address, copy that and test in your PC. If everything is fine, press Ctrl + p, Ctrl + q to exit the jenkins container.

## Result  
Now you can use the jenkins at the outside of local. ngrok looks simple and easy.  
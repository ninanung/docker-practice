# Docker practice

## Run in localhost  

Local envirenment is important for web developers. Docker will help you to set up.  
This is a sample project to deploy static web page locally.  

## Web and log  

Log is also important for debuging.  
This project make one simple service and one log server that get log from service.  

## Docker and compose  

Docker-compose is some kind of tool for automated running.  
You can set `port`, `image`, `volume` and many more.  
In this project, you can run DB and service server with docker-compose.  

## Deploy with docker-swarm  

I tried to deploy web service to docker swarm with docker-machine.  

## Jenkins with docker  

Test project to deploy jenkins server to internet with ngrok.  
Run jenkins server in the local docker container and start ngrok for port forwarding.  
Can connect to jenkins with randomly made URL.  

## Docker jenkins aws  

Deploy jenkins server with AWS and docker-machine.  
There's some function in the docker-machine to make docker server in AWS.  
Docker-machine allow user connect to docker server by IP address.  

## Docker swarm cluster  

Make 3 VM(docker server) and assign works to each docker machine when service request to server.  
Even can do health check before connect to server.  
With AWS and docker-swarm, you can make clustered AWS docker server in internet.  
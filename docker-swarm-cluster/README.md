# Docker sample  

## Prerequire  
1. VirtualBox install.
2. docker-machine install.
3. knowledge about docker, docker-machine and docker swarm

## Command  
```
make make-node
make ssh-1

//other terminal
make ssh-2

//other terminal
make ssh-3
```  
Make 3 nodes and connect to the each machine.  
```  
//in node1 terminal

docker swarm init --advertise-addr {this node's ip address}
//terminal will show you one command. copy and type it to all other nodes.
```  
That one command looks like `docker swarm join --token {random token} {node manager's ip address}`.  
`docker node ls` will show you the connection of nodes.  
```  
//in node1 terminal

docker service create --name whoami -p 4567:4567 subicura/whoami:1
```  
This command create service name 'whoami' with image name 'subicura/whoami:1'.  
`docker service ls` will show you what service is running now.  
```  
//in node1 terminal
curl node1:4567

//in node2 terminal
curl node2:4567

//in node3 terminal
curl node3:4567
```  
This 3 command show you same string. And that is node's id that running service now.  
It mean, all 3 node is connected and service running by node1, but all nodes can call the service from port 4567.  
This is not a clustering. Cause just one machine is running now, not clustered yet.  
```
docker service scale whoami=5
```  
This command will devide the whoami service to 5 scale. 
`docker service ps whoami` will show you the state of whoami service.  
You can now see 3 nodes share 5 scales.  
Ok then, do a 'curl' test once more. If it show you different result, what we want is done.  

## Healthcheck  
After version of docker 1.12 can set tha health check with Dockerfile. In this folder, difference of Dockerfile and Dockerfile.version1 is that part.  
```Dockerfile
HEALTHCHECK --interval=10s CMD wget -qO- localhost:4567
```  
This command will check the port 4567 is running. If not, return false.  

## Result  
I made the sample and simple server that return the node id.  
If you want, you can change the image. Or you can change the local server to AWS. I made the manual how to make AWS docker machine.  
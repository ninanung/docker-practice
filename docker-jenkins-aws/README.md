# Docker sample  

## Prerequire  
1. AWS(Amazon Web service) account.
2. docker-machine install.
3. knowledge about docker, docker-machine and AWS EC2.

## Command  
```
~$ docker-machine create \
--driver amazonec2 \
--amazonec2-access-key XXXXXXXXXXXXXXXXX \
--amazonec2-secret-key XXXXXXXXXXXXXXXXXXXXXXXXXXX \
--amazonec2-region ap-northeast-2 \
--amazonec2-vpc-id vpc-XXXXXXXXXX \
--amazonec2-open-port 8080 \
--amazonec2-open-port 50000 \
host
```  
There's no source code. only we need to do is this command.  

__docker-machine create__ : create docker-machine that can control with ssh connect.  
__--driver amazonec2__ : create with amazon EC2.  
__--amazonec2-access-key__ : access key for your accout connection.  
__--amazonec2-secret-key__ : another access secret key to connect.  
__--amazonec2-region ap-northeast-2__ : where do you want to deploy server. northeast-2 == seoul, korea.  
__--amazonec2-open-port__ : open port for this server. I open two ports that are 8080 and 50000(for jenkins, need these two ports).  
__host__ : name of instance in AWS and docker-machine.  

## Result  
Now i can connect to jenkins with internet, not local. I think i can also use this for web service.  

You can connect to my [jenkins page](http://13.209.18.97:8080/).
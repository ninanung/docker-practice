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

docker-machine create : create docker-machine that can control with ssh connect.  
--driver amazonec2 : create with amazon EC2.  
--amazonec2-access-key : access key for your accout connection.  
--amazonec2-secret-key : another access secret key to connect.  
--amazonec2-region ap-northeast-2 : where do you want to deploy server. northeast-2 == seoul, korea.  
--amazonec2-open-port : open port for this server. I open two ports that are 8080 and 50000(for jenkins, need these two ports).  
host : name of instance in AWS and docker-machine  

## Result  
Now i can connect to jenkins with internet, not local. I think i can also use this for web service.
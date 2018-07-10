# Docker sample

## Command  
```
docker build -t web-base -f Dockerfile.base /whewe/is/file/  
docker build -t web-image /where/is/dockerfile/
docker run -d -p 80:80 web-image  
```

## Result  
Make two docker images, one is for html file and httpd, another one is to run that server and files. Last, run second docker image in localhost:80.
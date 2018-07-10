# Docker sample

## Command  
```
docker build -t log-image /to/the/dockerfile
docker run -it --name log-container log-image
```
open another terminal
```
docker build -t web-image /to/the/dockerfile.web
docker build -d --name web-container -p 80:80 --volumes-from log-container web-image
```
back to first terminal
```
ls -l /var/log/httpd
cat /var/log/httpd/access_log
```

## Result  
I made two container, one for log, one for web. If someone access to web, log will go to the log-container and can see them. Log is really important for develop, so it will useful.

# Jenkins with docker: all architectures (arm64/amd64)

![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) 
![Jenkins](https://img.shields.io/badge/jenkins-%232C5263.svg?style=for-the-badge&logo=jenkins&logoColor=white)  
![Docker pulls](https://img.shields.io/docker/pulls/waterticket/jenkins-withdocker-all-architecture) 
![Docker Image Version (tag)](https://img.shields.io/docker/v/waterticket/jenkins-withdocker-all-architecture/latest)  

Dockerhub : [waterticket/jenkins-withdocker-all-architecture](https://hub.docker.com/r/waterticket/jenkins-withdocker-all-architecture)  

extends [getintodevops/jenkins-withdocker](https://hub.docker.com/r/getintodevops/jenkins-withdocker) with all architectures (arm64, amd64, etc,,)

# How to Use

```
docker pull waterticket/jenkins-withdocker-all-architecture:latest
docker run -d --restart unless-stopped \
  --name jenkins \
  -p 9090:8080 \
  -v ./data/:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock:ro \
  waterticket/jenkins-withdocker-all-architecture:latest
```
Jenkins data volume is `./data`  

Then jenkins runs in `localhost:9090`  
If you can't connect, check if the port 9090 is not blocked by the firewall.  
  

## Docker compose
```
---
version: '3.8'

services:
  jenkins:
    image: waterticket/jenkins-withdocker-all-architecture:latest
    container_name: jenkins
    privileged: true
    restart: unless-stopped
    ports:
      - "9090:8080"
    volumes:
      - ./data/:/var/jenkins_home
      - /var/run/docker.sock:/var/run/docker.sock:ro
```



# Get initial administrator password
```
docker exec -it jenkins /bin/sh -c "cat /var/jenkins_home/secrets/initialAdminPassword"
```

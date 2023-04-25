# jenkins-withdocker-all-architecture

extends [getintodevops/jenkins-withdocker](https://hub.docker.com/r/getintodevops/jenkins-withdocker) with all architectures (arm64, amd64, etc,,)

# How to Use

```
docker pull waterticket/jenkins-withdocker-all-architecture
docker run -d --restart unless-stopped -p 9090:8080 -v /var/run/docker.sock:/var/run/docker.sock waterticket/jenkins-withdocker-all-architecture --name jenkins
```
Then jenkins runs in `localhost:9090`  
If you can't connect, check if the port 9090 is not blocked by the firewall.


# Get initial administrator password
```
docker exec -it jenkins /bin/sh -c "cat /var/jenkins_home/secrets/initialAdminPassword"
```

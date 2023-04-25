# jenkins-withdocker-all-architecture

extends [getintodevops/jenkins-withdocker](https://hub.docker.com/r/getintodevops/jenkins-withdocker) with all architectures (arm64, amd64, etc,,)

# How to Use

```
docker pull waterticket/jenkins-withdocker-all-architecture
docker run -p 9090:8080 -v /var/run/docker.sock:/var/run/docker.sock waterticket/jenkins-withdocker-all-architecture --name jenkins
```
Then jenkins runs in `localhost:9090`

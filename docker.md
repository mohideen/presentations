title: Docker
author:
  name: Mohamed Mohideen
output: docker.html
controls: true
--

# Docker

--

### Containers

Linux containers is a generic term for an implementation of operating system-level virtualization for the Linux operating system. Currently, a number of such implementations exist, and they are all based on the virtualization, isolation, and resource management mechanisms provided by the Linux kernel, notably Linux namespaces and cgroups.



Source: Wikipedia

--

### Docker

Docker is a tool that can package an application and its dependencies in a virtual container that can run on any Linux server. This helps enable flexibility and portability on where the application can run, whether on premises, public cloud, private cloud, bare metal, etc.


Source: Wikipedia

--

### Dockerfile

```
FROM centos:7.3.1611 # Base box to start from
 
MAINTAINER mohideen@umd.edu # Email of the maintainer
 
RUN yum update -y && yum install vim -y # Command to run while building the image
 
ENV var1=someval var2=someval2 # Configure environment variables
 
VOLUME /data # Configure persistent volume (That persists accross container destruction)

EXPOSE 80 # Make a port avaiable for mapping to host machine or linking to another container

CMD ["echo", "Hello World"] # Command to run while starting the container
 
# Alternatively, ENTRYPOINT can be used instead of CMD which would make overriding the CMD at runtime more explicit. Commands will be interpretted as args instead.
#ENTRYPOINT ["echo"]
```
Building and Running
```
$ docker build -t helloimage:0.1 .
$ docker run -it -p 5001:80 --name hellocon helloimage:0.1 # Maps port 80 from container to 5001 on host. (-P option can be used for random mapping)
```
--

### Multi container apps
* Docker recommends isolating each major component of the application to a separate container.
* Docker Compose helps manage multiple containers.

--
### Docker Compose File
```
version: '3'
services:
  web:
    build: .
    ports:
    - "5000:5000"
    volumes:
    - .:/code
    - logvolume01:/var/log
    links:
    - redis
  redis:
    image: redis
volumes:
  logvolume01: {}
```
https://docs.docker.com/compose/overview/

--

### Docker: Hello SSDR
Download and install docker: https://download.docker.com/mac/stable/Docker.dmg

Hello World Example:
```
docker container run hello-world
```

Hello SSDR Example:
```
docker container run centos /bin/bash -c "echo 'Hello SSDR'"
```

--

### Demo: Annual Statting Request
* Dockerfile: https://github.com/umd-lib/annual-staffing-request/blob/dockerized/Dockerfile
* Docker Compose: https://github.com/umd-lib/annual-staffing-request/blob/dockerized/docker-compose.yml
--

### Demo: Annual Statting Request
Checkout the Annual Staffing Request `dockerized` branch:
```
git clone https://github.com/umd-lib/annual-staffing-request.git
cd annual-staffing-request
git checkout dockerized
```
Running Annual Staffing Request with Docker:
```
# Build
docker-compose build
# Start
docker-compose up -d
# List containers
docker-compose ps
# Stop
docker-compose down
```
--

### Portainer
* A simple management UI for Docker
* http://docker-sandbox.lib.umd.edu:9000/#/auth
* https://portainer.io/

--

### Docker Registry
* A Nexus like app for storing and distributing docker images.
* https://docs.docker.com/registry/

--

### Documentation
* General: https://confluence.umd.edu/display/LIB/Docker

* Installation Notes: https://confluence.umd.edu/pages/viewpage.action?pageId=552502059

* Open Questions: https://confluence.umd.edu/display/LIB/Open+Questions

--

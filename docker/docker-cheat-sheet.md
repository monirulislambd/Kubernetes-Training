# Docker CLI Cheatsheet

This cheatsheet provides common Docker CLI commands for managing containers, images, and viewing information and stats.

## Run a New Container

Start a new container from an image:
```bash
docker run IMAGE
docker run nginx

```
...and assign it a name:
```bash
docker run --name CONTAINER IMAGE
docker run --name web nginx
```

...and map a port:
```bash
docker run -p HOSTPORT:CONTAINERPORT IMAGE
docker run -p 8080:80 nginx
```

...and map all ports:
```bash
docker run -P IMAGE
docker run -P nginx
```

...and start container in background:
```bash
docker run -d IMAGE
docker run -d nginx
```

...and assign it a hostname:
```bash
docker run --hostname HOSTNAME IMAGE
docker run --hostname srv nginx
```

...and add a DNS entry:
```bash
docker run --add-host HOSTNAME:IP IMAGE
```

...and map a local directory into the container:
```bash
docker run -v HOSTDIR:TARGETDIR IMAGE
docker run -v ~/:/usr/share/nginx/html nginx
```

...but change the entrypoint:
```bash
docker run -it --entrypoint EXECUTABLE IMAGE
docker run -it --entrypoint bash nginx
```

## Manage Containers

Show a list of running containers:
```bash
docker ps
```

Show a list of all containers:
```bash
docker ps -a
```

Delete a container:
```bash
docker rm CONTAINER
docker rm web
```

Delete a running container:
```bash
docker rm -f CONTAINER
docker rm -f web
```

Delete stopped containers:
```bash
docker container prune
```

Stop a running container:
```bash
docker stop CONTAINER
docker stop web
```

Start a stopped container:
```bash
docker start CONTAINER
docker start web
```

Copy a file from a container to the host:
```bash
docker cp CONTAINER:/SOURCE TARGET
docker cp web:/index.html index.html
```

Copy a file from the host to a container:
```bash
docker cp TARGET CONTAINER:/SOURCE
docker cp index.html web:/index.html
```

Start a shell inside a running container:
```bash
docker exec -it CONTAINER EXECUTABLE
docker exec -it web bash
```

Rename a container:
```bash
docker rename OLD_NAME NEW_NAME
docker rename 096 web
```

Create an image out of a container:
```bash
docker commit CONTAINER
docker commit web
```

## Manage Images

Download an image:
```bash
docker pull IMAGE[:TAG]
docker pull nginx
```

Upload an image to a repository:
```bash
docker push IMAGE
docker push myimage:1.0
```

Delete an image:
```bash
docker rmi IMAGE
```

Show a list of all images:
```bash
docker images
```

Delete dangling images:
```bash
docker image prune
```

Delete all unused images:
```bash
docker image prune -a
```

Build an image from a Dockerfile:
```bash
docker build DIRECTORY
docker build .
```

Tag an image:
```bash
docker tag IMAGE NEWIMAGE
docker tag ubuntu ubuntu:18.04
```

Build and tag an image from a Dockerfile:
```bash
docker build -t IMAGE DIRECTORY
docker build -t myimage .
```

Save an image to a tar file:
```bash
docker save IMAGE > FILE
docker save nginx > nginx.tar
```

Load an image from a tar file:
```bash
docker load -i TARFILE
docker load -i nginx.tar
```

## Info & Stats

Show the logs of a container:
```bash
docker logs CONTAINER
docker logs web
```

Show stats of running containers:
```bash
docker stats
```

Show processes of a container:
```bash
docker top CONTAINER
docker top web
```

Show installed Docker version:
```bash
docker version
```

Get detailed info about an object:
```bash
docker inspect NAME
docker inspect nginx
```

Show all modified files in a container:
```bash
docker diff CONTAINER
docker diff web
```

Show mapped ports of a container:
```bash
docker port CONTAINER
docker port web
```

---

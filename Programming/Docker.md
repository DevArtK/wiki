# Docker

## Table Contents
[Mult Command Containers](Mult-Command_Containers)

## Basic Commands


### Creating + Running Containers

**Create a Container**

Focused on preparing/creating the container filesystem
```bash
$ docker create <image_name>
---
- docker : references the docker client
- create : try to create container
- image_name : name of image to use to create a new container
```

**Start a Container**

Focused on starting it and executing a command
*Does not show logs and output by default*

```bash
$ docker start -a <container_id>
---
- docker : references the docker client
- start : try to start an existing container
- -a : watch for output and print it to host terminal
- container_name : id of container to start
```

**Create & Start a Container**

*By default shows all the logs and output after execution*
```bash
$ docker run <image_name>
---
- docker : references the docker client
- run : try to create and run a container
- image_name : name of image to use for this container

docker run = docker create + docker start
```



**Create + Run a Container From an Image and Override Default Command**

*Once a container is create with a default command, it cannot be replaced; a new
container must be created and a different default command must be specified*

```bash
$ docker run <image_name> <command>
---
- <command> : overrides default command provided by image
```

*Example*

```bash
$ docker run busybox echo Hi There! : echo out text
$ docker run busybox ls : list files/folders of root dir of container
```


### Managing Running Containers

**List Running Containers**

```bash
$ docker ps
```

**List All Containers**
```bash
$ docker ps -a
or
$ docker ps --all
```



### Removing Stopped Containers

**Delete Stopped Containers**
```bash
docker system prune
```

This will delete :
- all stopped containers
- all networks not used by at least one container
- all dangling images
- all build cache



### Retrieving Log Outputs

*This does not restart the container*
Retrieves the record left by container
```bash
$ docker logs <container_id>
---
- logs : retrieves the container logs of a specific container
```



### Stopping Containers

Stop a running container with either :
```
$ docker stop <container_id>
- sends SIGTERM message, terminate signal to shutdown on it's own time with
  cleanup or emit some message
- if the container doesn't automatically stop in 10 secs, docker will issue a
  kill command

okr

$ docker kill <container_id>
- sends SIGKILL message, kill signal to primary running process, doesn't wait
```

*Example*
```bash
$ docker create busybox ping google.com
$ docker start <container_id>
$ docker logs <container_id>

$ docker stop <container_id>
or
$ docker kill <container_id>
```

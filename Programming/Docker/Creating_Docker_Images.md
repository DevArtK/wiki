# Creating Custom Docker Images

*Dockerfile* : Configuration to define how a container should behave

*Docker Client* : Once a Dockerfile is created it gets passed to the docker cli

*Docker Server* : Docker cli provides the file to the docker server, takes
dockerfile and all its configuration and builds a usable image that can be used
to create containers

*Usable Images* : Allows to build multiple containers off the same image



## Steps to Creating a Basic Dockerfile

1. Specify a base image
2. Run some commands to install additional programs
3. Specify a command to run on container startup



## Redis Dockerfile
```Dockerfile
FROM alpine
RUN apk add --update redis
CMD ["redis-server"]
```

**Build Image From Dockerfile**

*Note* : Terminal directory is where the Dockerfile is located or specify
location of Dockerfile

```bash
$ docker build -t <unique_image_identifier> .
```
The *unique image identifier* should be in the format of : ```<personal_docker_id>/<repo/project name>:version```
- Version is optional

    Example : devart/redis_test:latest

- "." : is the build context


After the initial FROM instruction, each step will create a intermediate
container, take a snapshot of the fs and/or primary running command (RUN)
and pass it onto the next step till Dockerfile instructions are completed
and return the final built container



## Copying Build Files

```Dockerfile
COPY <host_dir> <container_dir>
COPY ./ ./
```

- host_dir : Path to folder to copy from host machine, releative to build
  context which was specified by the docker build command
- container_dir : Destination inside container
- to prevent unecessary rebuilds, split any package manager install files and
  install into their own section prior to copying over all files



## Port Mapping
Requests made by the container to the outside world are done without having to
specify an ports

Communication from the outside world to the container need to be opened, to
forward the traffic to a specific port in a container a ports need to be
specified

Port forwarding is not setup in the Dockerfile, it is strictly a runtime
constraint

**Docker Run with Port Mapping**

```bash
Syntax :
    $ docker run -p host_port:container_port <image_id>
Example:
    $ docker run -p 8000:8080 <image_id>
```

- host_port : Route incoming request to this port on local host
- container_port : to this port inside the container

The port from host the machine and the port on the container do no have to be
the same



## Specifying Working Directory

```Dockerfile
WORKDIR <path_in_container>
```
Path in container can be anything, if it does not exist it will be created

Once working directory is specified (let's say /app) it will be used to any subsequent commands
such as :
```
$ docker exec -it <container_id> sh
```
Which would result the shell starting in /app directory

So the workdir setting not only affects commands executed in the Dockerfile but also commands executed
with docker exec command



## Avoid Unnecessary Rebuilds / Minimizing Cache Busting and Rebuilds
Possible to avoid longer rebuilds by splitting up the copy and run commands.

Look at below example



## Final Dockerfile
```Dockerfile
FROM node:alpine
WORKDIR /var/app
COPY ./package.json ./
RUN npm install
COPY ./ ./
CMD [ "npm", "start" ]
```

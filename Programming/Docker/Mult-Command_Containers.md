# Multi-Command Containers

*Example using Redis*

```bash
- Pull + Create + Run redis server
$ docker run redis
```

Problem is there Redis-CLI is required to access the redis database
(redis-server)

**Executing Commands/Additional Command in a Container**

```bash
$ docker exec -it <container_id> <command>
---
- -it : allows the ability to provide input to the container
```

*Example using -it flag*
- Verify that the container is still running & get container id : docker ps
- Execute redis-cli on running redis container
    - This will start-up a 2nd, running program inside the container
- The "-it" flags allows to send commands to a container

```
docker exec -it <container_id> redis-cli
```

### Purpose of the "-it" Flags

Every process created in a Linux environment has 3 communication channels
attached to it

1. STDIN : Pass information to the process
2. STDOUT : Conveys information coming out of the process
3. STDERR : Conveys information out of the process, only if there are error(s)

These channels are used to communicate information either into the process or
out of the process


- -i : Attaches host terminal to STDIN channel to a process/container
- -t : All text coming in and out is pretty formatted

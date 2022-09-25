# Manual Image Creation

Don't want to do this in general in production environment

Run a Base Image
``` bash
$ docker run -it alpine sh
```


Manually install redis

``` bash
$ apk add --update redis
```
Exit Container


Get Id of Running Container

```bash
$ docker ps
```


Commit Changes to Container
```bash
$ docker commit -c 'CMD' ["redis-server"] <container_id>
```


Start Updated Container After Commit

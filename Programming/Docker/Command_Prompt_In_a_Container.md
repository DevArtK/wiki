# Terminal Access to a Running Container


**Opening a Shell on a Running Container**

For more minimal containers
```bash
$ docker exec -it <container_id> sh
```

or

For more complete containers
```
$ docker exec -it <container_id> bash
```



**Starting a Container and a Shell**

*Note : Prevents from a default command/program from running*

```bash
$ docker run -it <image_name> sh

or

$ docker run -it <image_name> bash
```

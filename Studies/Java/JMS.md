# JMS

## ActiveMQ : Message Broker

### Install ActiveMQ: Message Broker

```bash
$ docker pull rmohr/activemq
$ docker run -p 61616:61616 -p 8161:8161 rmohr/activemq
```

### Customizing Configuration and Persistence Location
By default data and configuration is stored inside the container and will be
lost after the container has been shut down and removed. To persist these files
you can mount these directories to directories on your host system

```bash
docker run -p 61616:61616 -p 8161:8161 \
    -v /your/persistent/dir/conf:/opt/activemq/conf \
    -v /your/persistent/dir/data:/opt/activemq/data \
    rmohr/activemq
```

ActiveMQ expects that some configuration files already exists, so they won't be
created automatically, instead you have to create them on your own before
starting the container. If you want to start with the default configuration you
can initialize your directories using some intermediate container:

```bash
docker run --user root --rm -ti \
    -v /your/persistent/dir/conf:/mnt/conf \
    -v /your/persistent/dir/data:/mnt/data \
    rmohr/activemq:5.15.4-alpine /bin/sh
```

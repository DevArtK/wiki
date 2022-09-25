# Docker Setup



## Arch Based Install

### Install
```bash
$ sudo pacman -S docker
$ sudo groupadd docker
$ sudo usermod -aG docker $USER
-- If socket permission denied error after running :
$ docker info
$ sudo chmod 666 /var/run/docker.sock
```

###  Enable Docker on Startup

```bash
$ sudo systemctl enable docker.service
$ sudo systemctl enable containerd.service
```

### Disable on Startup

```bash
$ sudo systemctl disabled docker.service
$ sudo systemctl disabled containerd.service
```

# SSH Key Generation
Get up and going with SSH Keys

## Generate a Key

### ED25519

```bash
$ ssh-keygen -o -a 100 -t ed25519 -f ~/.ssh/id_ed25519 -C "comment"
```


### RSA

```bash
$ ssh-keygen -t rsa -b 4096
```

## Add Key to Agent

A specific key
```bash
$ ssh-add ~/.ssh/id_<key>
```

All keys, defaults to ```~/.ssh``` directory
```bash
$ ssh-add
```

## General Key Commands


### Check Available Keys On Host
```
$ for key in ~/.ssh/id_*;do ssh-keygen -l -f "${key}"; done | uniq
```


### Generate / Re-generate Host Keys


```bash
$ ssh-keygen -A
```

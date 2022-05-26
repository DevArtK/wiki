# GPG Keys

## Installation

Arch

```bash
sudo pacman -S gnupg
```



## Configuration
GnuPG home directory is where the GnuPG suit stores its keyrings and private
keys + reads from them

Default Path/Directory : ~/.gnupg

Home directory permissions are 700
Files the home directory contains are 600
- Only the owner of the directory has permission to read, wire, and access the
  files


### Configuration files

User: ```$gnupg_home/gpg.conf```
Global: ```/etc/gnupg/gpg.conf```

## Commands

**List Keys in Public Keyring**

```bash
gpg --list-keys
```


**List Keys in your Secret Keyring**

```bash
gpg --list-secret-keys
```

**Export Public Key**

```bash
gpg --export --armor --output --no-emit-verison public.key user-id
```


**Import a Public Key**

```bash
gpg --import public.key
```

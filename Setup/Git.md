# Git Setup

1. Generate an SSH Key
[SSH_Key](Keys/SSH_Keys)

2. Install Git
```
sudo apt-get install git
sudo pacman -S git
```


3. Start SSH Agent + Add Generated Key
4.
```bash
$ eval "$(ssh-agent -s)"
$ ssh-add <ssh_key_name>
```

4. Test Git Connection
5.
```bash
$ ssh -T git@github.com
```

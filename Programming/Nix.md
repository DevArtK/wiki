# Nix Shell


## Install
```
$ sh <(curl -L https://nixos.org/nix/install)
. /home/prometheus/.nix-profile/etc/profile.d/nix.sh
```

**Official Package List**
```
https://search.nixos.org/packages
```

**Searching Package Attribute Names**
Packages can be searched for through the terminal
Example, search for git :
```
$ nix-env -qaP git
```

*Results*
```
gitAndTools.gitFull  git-2.25.0
gitMinimal           git-2.25.0
```
- The first column is the attribute name
- The second column is the package name and its version
- The query used for searching packages is regex, so be aware when it comes to
  special characters

It is also possible to add your own packages, and/or custom shell aliases


**Example Working Towards Reproducibility**
```
$ nix-shell --pure -p git -I nixpkgs=https://github.com/NixOS/nixpkgs/archive/2a601aafdc5605a5133a2ca506a34a3a73377247.tar.gz
```
- The ```pure``` flag makes sure that the bash environment from your system is
  not inherited, useful for one-liners, or scripts that run within a CI
  environment for example. However while developing, we'd like to have our
  editor around and a bunch of other things. Therefore we might skip this flag
  for development environment but use it for in build ones
- The ```-I``` flag pins the nixpkgs revision to an **exact Git revision**
  leaving no doubt about which exact version of Nix packages will be used


**Reproducible Executables**
Possible to wrap scripts with Nix to provide reproducible shell environments
that we can commit to a Git repository and share with anyone online.

- As long as they have Nix installed, they'll be able to execute the script
  without worrying about manually installing (and later uninstalling)
  dependencies at all

```
#! /usr/bin/env nix-shell
#! nix-shell --pure -i python -p "python38.withPackages (ps: [ ps.django  ])"
#! nix-shell -I
nixpkgs=https://github.com/NixOS/nixpkgs/archive/2a601aafdc5605a5133a2ca506a34a3a73377247.tar.gz

import django

print(django)
```

This is essentially the same example as in previous section, but this time
declaratively source controlled

All of the required Nix commands are included as ```#!``` shebang headers in the
script itself

Note : The multi-line shebang format is a feature of nix-shell. All subsequent ```#! nix-shell``` lines are used to build up the shell's configuration before
building the shell and executing the body of the script



## Dependency Management with Niv
Allows for more automation around bumping dependencies, including Nixpkgs; niv
is made for exactly that

Niv itself is available in ```nixpkgs``` so using it is simple :
```
$ nix-shell -p niv --run "niv init"
```
This command will generate ```nix/sources.json``` with information about how and
where dependencies are fetched.

It will also create ```nix/sources.nix```, which glues the sources together in
Nix, which glues the sources together in Nix

**View version of Niv**
```
$niv show
```

**Change Tracking Branch to the one you like**
```
$ niv modify modify nixpkgs --branch nixos-21.05
```

You can use the generated ```nix/sources.nix``` with a top-level default.nix
```
{ source ? impor ./nix/sources.nix
, pkgs ? import sources.nixpkgs {}
}:
```

**Update All Dependencies by running :
```
$ nix-shell -p niv --run "nix update"
```

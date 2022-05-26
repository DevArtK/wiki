# Pass - The Standard Unix Password Manager

All passwords located : ~/.password-store

GPG Keys : ~/.password-store/.gpg_id
- Multiple gpg keys can be specified, one per line

Extensions : ~/.password-Commands-store/.extensions
- Directory that contains extension files

### Generate GPG Key
    [Key Generation](Key Generation)

### Commands
| Command                    | Function                                  |
| ---                        | ---                                       |
| pass                       | List all existing passwords in store      |
| pass Some/app              | Show password of Directory/app            |
| pass -c Some/app           | Copy password to clipboard from Some/app  |
| pass insert Path/tosave    | Insert a single line password to location |
| pass insert -m Path/tosave | Insert multi-line password to location    |
| pass generate Path/tosave  | Auto generate a password for Path/tosave  |
| pass rm Path/toremove      | Remove a password from Path/tosave        |
|                            |                                           |

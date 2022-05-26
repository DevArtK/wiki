# GPG

Use version 2.1

Command generates a key pair that consists of a public & private key
``` bash
$ gpg --gen-key
```

## Process

1. Run command
```bash
$ gpg2 --gen-key
```

2. Specify key type
- Almost always use RSA

3. For key size, select between 1024 and 4096 bit long
- The default is 2048

4. Choose when the key will expire
- It is possible to change the expiration date after key creation

5. Confirm correct

6. Enter name & email for GPG key
- This is what will authenticate you as real individual
- If using the GPG key for self-introduction on a mailing-list, enter email
  address you use on that list
- Use comment field to include aliases or other information

7. Confirm with 0, enter passphrase

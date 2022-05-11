# GPG
GPC basically its a encryption and decryption tool based on assymetrical keys

### Generate a Key
```sh
gpg --gen-key
```

### See your keys
```sh
gpg -k #Show your public  keys
gpg -K #Show your private keys
```

### Export a Key
```sh
gpg --export --armor -o <name>.pub
```

### Import a key
```sh
gpg --import --armor <name>.pub
```

### Encrypt a file
```sh
gpg -e -r <email> <file> 
```

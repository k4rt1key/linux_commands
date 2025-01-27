# ssh in linux

SSH (Secure Shell) is a cryptographic network protocol used for securely accessing and managing remote systems over an unsecured network. It provides a secure channel over an insecure network by encrypting the data transmitted between the client and the server.

```bash
ssh [username]@[remote_host] 
ssh -p 2222 [username]@[remote_host] # specifying port
```

## ssh with private keys

```bash
# generating private keys
ssh-keygen -t rsa -b 4096
ssh-copy-id [username]@[remote_host]
# now ssh into any device
ssh [username]@[remote_host]
```

## ssh config

```bash
~/.ssh/config
```

```bash
Host myserver
    HostName 192.168.1.100
    User user
    Port 2222
    IdentityFile ~/.ssh/id_rsa
```

Now we can ssh using 

```bash
ssh myserver
```


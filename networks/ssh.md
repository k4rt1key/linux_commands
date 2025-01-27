# ssh in linux

SSH (Secure Shell) is a cryptographic network protocol used for securely accessing and managing remote systems over an unsecured network. It provides a secure channel over an insecure network by encrypting the data transmitted between the client and the server.

```bash
ssh [username]@[remote_host] 
ssh -p 2222 [username]@[remote_host] # specifying port
```

## ssh with private keys

```bash
# generating private keys
sudo apt update
sudo apt install openssh-server

ssh-keygen -t rsa -b 4096

# ~/.ssh/id_rsa

ssh-copy-id [username]@[remote_host]
#or
cat ~/.ssh/id_rsa.pub
echo "public-key-content" >> ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys

sudo nano /etc/ssh/sshd_config

# set
PubkeyAuthentication yes
AuthorizedKeysFile .ssh/authorized_keys
PasswordAuthentication no

sudo systemctl restart sshd

```

```bash
ssh -i /a/b/c/key hostname@ip

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


### how to findout ssh in our system

```bash
who
```

#### output 
```
kartikey :0           2025-01-26 11:30 (:0)
kartikey pts/1        2025-01-27 11:56 (10.20.41.113)
```


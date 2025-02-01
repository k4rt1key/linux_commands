# SSH in Linux

SSH (Secure Shell) is a cryptographic network protocol used for securely accessing and managing remote systems over an unsecured network. It provides a secure channel by encrypting the data transmitted between the client and the server.

---

## Basic SSH Usage

To connect to a remote host using SSH:

```bash
ssh [username]@[remote_host]
ssh -p 2222 [username]@[remote_host] # to speify port
```

## SSH with private keys

```bash
# STEP 1 : INSTALLATION 
sudo apt update
sudo apt install openssh-server

# STEP 2 : GENERATING PRIVATE KEYS
ssh-keygen -t rsa -b 4096

# STEP 3 : COPY PUBLIC KEY TO AUTHORISED KEYS
ssh-copy-id [username]@[remote_host]

# OR 

cat ~/.ssh/id_rsa.pub
echo "public-key-content" >> ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys

# STEP 4 : CHANGE CONFIG FILE
sudo nano /etc/ssh/sshd_config

# SET 
PubkeyAuthentication yes
AuthorizedKeysFile .ssh/authorized_keys
PasswordAuthentication no

# STEP 5 : RESTART SERVICE
sudo systemctl restart sshd


# STEP 6 : SSH WITH PRIVATE KEY
ssh -i /path/to/key hostname@ip
```


### How to findout who is SSHed into our system

```bash
who
```

**Output will looks like this :**

```
kartikey :0           2025-01-26 11:30 (:0)
kartikey pts/1        2025-01-27 11:56 (10.20.41.113)
```


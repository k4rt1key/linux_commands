# command ftp

## setup
```bash
sudo apt install vsftpd
sudo nano /etc/vsftpd.conf
sudo systemctl start vsftpd
sudo systemctl enable vsftpd

# uncomment or add 
```

```bash
# open config file
sudo nano /etc/vsftpd.conf


```

```
# enable this 
anonymous_enable=NO
local_enable=YES
write_enable=YES
chroot_local_user=YES
```

```bash
# restart
sudo systemctl restart vsftpd
```
**add user**
```bash
sudo adduser ftpuser
sudo passwd ftpuser
```

```bash
sudo chown ftpuser:ftpuser /home/ftpuser

```

```bash
ftp [server_ip_or_host_name]
ftp> user [username] # login into username
ftp> get [filename] # get that filename
ftp> put [filename] # put that filename
ftp> cd [dir] # change dir
ftp> lcd [dir] # change dir in local machine
ftp> quit
```

```bash
# lftp for ftps
lftp -u [username],[password] ftps://[serverip_or_host_name]
lftp> get [filename]
lftp> put [filename]
exit
```

```bash
scp [localfile] [username]@[ip]:[directory]
scp -r [localfile] [username]@[ip]:[directory] # for recursively copy a directory
scp -P [port] [localfile] [username]@[ip]:[directory]
```
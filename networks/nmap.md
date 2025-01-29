# nmap

- Discovers network and creates map of it 
- Used for detecting open ports 

```bash
nmap -sn 192.168.1.0/24
nmap -sn -p 1234,5000,6000 192.168.1.0/24
nmap -Pn -p 1-65535 10.20.41.115
```

- sn (Ping Scan)
Purpose: The -sn option tells Nmap to perform a host discovery scan only, without scanning ports. It checks if the host is alive by sending ICMP Echo Requests (ping) or other probes, depending on the network conditions and the options used.

- Pn (No Ping)
Purpose: The -Pn option tells Nmap not to perform any host discovery. It assumes that the target is up and skips the initial ping phase. This is useful if you are scanning a host that is behind a firewall or network device that blocks ping requests.



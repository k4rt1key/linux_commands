# nmap

- Discovers network and creates map of it 
- Used for detecting open ports 

# - sn (Ping Scan)
```bash
nmap -sn [ip]
nmap -sn [ip]/[mask]
nmap -sn -p [port1,port2,... || portN-portM] [ip]/[mask]
```

**Purpose:** 
- The -sn option tells Nmap to perform a host discovery scan only, without scanning ports. It checks if the host is alive by sending ICMP Echo Requests (ping) or other probes, depending on the network conditions and the options used.

# Pn (No Ping)

```bash
namp -Pn [ip/subnet]
namp -Pn -p [port1,port2,... || portN-portM] [ip]/[subnet]
```

**Purpose:**
- The -Pn option tells Nmap not to perform any host discovery. It assumes that the target is up and skips the initial ping phase. This is useful if you are scanning a host that is behind a firewall or network device that blocks ping requests.



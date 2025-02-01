# nslookup

- Used to query DNS server to obtain domain name or ip

```bash
nslookup google.com 
nslookup -type=A google.com # IPV4
nslookup -type=AA google.com # IPV4 & IPV6
```

## OUTPUT

```
Server:         127.0.0.53
Address:        127.0.0.53#53

Non-authoritative answer:
Name:   google.com
Address: 142.250.183.46
Name:   google.com
Address: 2404:6800:4009:820::200e
```


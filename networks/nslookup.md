# nslookup

- Used to query DNS server to obtain domain name or ip

```bash
nslookup google.com
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

```bash
nslookup -type=A google.com # ipv4
nslookup -type=AA google.com # ipv4 and 6
nslookup -type=MX google.com  # for mail exchange server
nslookup -type=NS google.com  # for name server
nslookup -type=MX google.com  # for mail exchange server
```
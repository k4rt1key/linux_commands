# systemd-resolve 

- Domain information groper
- For Query DNS

## For getting stats about dns cache

```bash
sudo resolvectl statistics # for getting stats about dns cache
```

**OUTPUT**

```
DNSSEC supported by current servers: no

Transactions              
Current Transactions: 0   
  Total Transactions: 8926
                          
Cache                     
  Current Cache Size: 105 
          Cache Hits: 1043
        Cache Misses: 1177
                          
DNSSEC Verdicts           
              Secure: 0   
            Insecure: 0   
               Bogus: 0   
       Indeterminate: 0   
```

## To resolve query

```bash
sudo systemd-resolve google.com 
# === OR ===
resolvectl query google.com
```

**OUTPUT**

```
google.com: 142.250.70.46                      -- link: wlp0s20f3

-- Information acquired via protocol DNS in 3.2ms.
-- Data is authenticated: no
```

## To flush dns-cache

```bash
sudo systemd-resolve --flush-caches 
```

# dig

```bash
dig google.com AAAA # for ipv6
dig google.com ns # for getting all nameservers for this domain
dig @8.8.8.8 example.com # for using diff dns server ( default is 127.0.0.53:53) 
dig google.com mx # for getting all mailserver for this domain 
dig -x 8.8.8.8 # for reverse query 
```



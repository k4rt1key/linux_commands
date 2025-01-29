# dig 
Domain information groper

- For Query DNS

```bash
sudo systemd-resolve --statistics
# for getting stats about dns cache

sudo systemd-resolve google.com 
# or 
resolvectl query google.com
# to view the cache entry for a specific domain

sudo systemd-resolve --flush-caches # to flush cache
```

```bash
dig google.com AAAA # for ipv6
dig google.com 
dig google.com ns # for getting all nameservers for this domain
dig @8.8.8.8 example.com # for using diff dns server ( default is 127.0.0.53:53) 
dig example.com mx # for getting all mailserver for this domain 
dig -x 8.8.8.8 # for reverse query 
```



# ping

```bash
ping 
ping -c 4 # how many packets to send
ping -i <interval> # Sets the interval between sending packets. ( in seconds )
ping -s <size> # Specifies the size of the packet to send. ( in bytes )
ping -t <hops> # Specifies time to live ( number of hops packets can take )
```

- If we specifies data size by using ` ping -s 100 ` 
    - It will send 128 bytes of data insted of 100 because 28 bytes used for ICMP headers

### OUTPUT 

```
PING google.com (142.250.192.78) 56(84) bytes of data.
64 bytes from bom12s16-in-f14.1e100.net (142.250.192.78): icmp_seq=1 ttl=113 time=23.6 ms
64 bytes from bom12s16-in-f14.1e100.net (142.250.192.78): icmp_seq=2 ttl=113 time=68.7 ms
64 bytes from bom12s16-in-f14.1e100.net (142.250.192.78): icmp_seq=3 ttl=113 time=28.7 ms
64 bytes from bom12s16-in-f14.1e100.net (142.250.192.78): icmp_seq=4 ttl=113 time=54.0 ms
64 bytes from bom12s16-in-f14.1e100.net (142.250.192.78): icmp_seq=5 ttl=113 time=31.5 ms

--- google.com ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4007ms
rtt min/avg/max/mdev = 23.625/41.308/68.667/17.194 ms
```

mdev = Mean Deviation


# fping 
- Can handle multiple hosts 
- Faser in execusion
- Can customize

```bash
fping -a google.com cl1p.in stayinit.in # prints alive hosts 
fping -g 10.20.40.1 10.20.40.255 # pings range of ips
fping -g 10.20.40.0/24 # pings range of ips using subnet
fping -f file.txt # reading hostnames from file
fping -t 32 cl1p.in # sets timeout
fping -s cl1p.in # see stats
fping -p 5 cl1p.in # how many time it waits before sending packets
fping -c 1 cl1p.in # number of packets to send each target
```
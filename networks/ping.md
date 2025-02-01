# ping

```bash
ping 
ping -c 4 # Stop after sending 4 ECHO_REQUEST
ping -i <interval> # Interval between sending each packets. ( in seconds )
ping -t <hops> # Specifies TTL
```


# fping 

- Can handle multiple hosts 

```bash
fping -a google.com cl1p.in stayinit.in # Prints alive hosts

fping -g 10.20.40.1 10.20.40.255 # Pings range of IP
fping -g 10.20.40.0/24

fping -t 32 cl1p.in # Timeout

fping -f file.txt # Reading hostnames from file
fping -s cl1p.in # Displaying stat
fping -p 5 cl1p.in # Same as -i in ping
fping -c 1 cl1p.in # Same as ping
```
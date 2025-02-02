# ip 

- Show / manipulate routing and network devices.

## To show network info

```bash
ip addr # ip addresses

ip route # routing table
ip route show dev [interface-name]

ip link # network devices
```

# To add route

```bash
sudo ip route add [dest] via [gateway] dev [interface_device]
```

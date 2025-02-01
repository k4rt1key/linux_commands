# netstat 

- Used for viewing network connections, routing tables, interface stats

```bash
netstat
netstat -a # for viewing active connection
netstat -l # for viewing open ports
netstat -r # for viewing router table
netstat -p # for viewing process to port mapping
netstat -i # for viewing network interface statistics

netstat -s # for viewing network protocol wise stats
```

## netstat -tunlap

```
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      -                   
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      -                   
tcp        0      0 10.20.40.28:47928       52.108.44.3:443         ESTABLISHED 3087/chrome --type= 
tcp        0      0 10.20.40.28:35608       20.189.173.9:443        ESTABLISHED 3443/Code --standar 
tcp        0      0 10.20.40.28:43178       172.64.155.209:443      ESTABLISHED 3087/chrome --type= 
tcp        0      0 10.20.40.28:38616       172.64.152.233:443      ESTABLISHED 3087/chrome --type= 
tcp        0      0 10.20.40.28:55794       52.123.168.134:443      ESTABLISHED 3087/chrome --type= 
```


- Recv-Q = Number of bytes in receive queue
- Send-Q = Number of bytes in send queue
- Foreign Address = Ip of destination
- State = State of connection
    - LISTEN → Waiting for incoming connections.
    - ESTABLISHED → Active connection, data transfer ongoing.
    - TIME_WAIT → Closed, waiting to ensure all packets are received.
    - CLOSED → Connection fully terminated.

## netstat -r

```
Kernel IP routing table
Destination     Gateway         Genmask         Flags   MSS Window  irtt Iface
default         _gateway        0.0.0.0         UG        0 0          0 wlp0s20f3
10.20.40.0      0.0.0.0         255.255.252.0   U         0 0          0 wlp0s20f3
link-local      0.0.0.0         255.255.0.0     U         0 0          0 wlp0s20f3
```

- Gateway 0.0.0.0 means no gateway is used (direct communication).
- Flags → Indicates route status:
    - U: The route is up and operational.
    - G: The route uses a gateway (default route).
- MSS = Max Segment size 
- Window = Window size for TCP
- irtt = Initial round trip time


**Private ip vs Link local ip**

**Private ip**
- Assigned manually or via DHCP.
- Requires a Gateway ? YES to communicate outside the local network.
- Not directly accessible, requires NAT to reach the internet.

**Link local ip**
- Self-assigned when no DHCP server is available.
- Requires a Gateway ? No,direct communication within the same link.
- Never accessible on the internet, always local.


# netstat -i

```
Kernel Interface table
Iface      MTU    RX-OK RX-ERR RX-DRP RX-OVR    TX-OK TX-ERR TX-DRP TX-OVR Flg
enp0s31f  1500        0      0      0 0             0      0      0      0 BMU
lo       65536    24619      0      0 0         24619      0      0      0 LRU
wlp0s20f  1500   882554      0  14711 0        204616      0      0      0 BMRU
```


| **Column**   | **Description**                                                                 |
|--------------|---------------------------------------------------------------------------------|
| **Iface**    | The name of the network interface (e.g., `enp0s31f`, `lo`, `wlp0s20f`).         |
| **MTU**      | Maximum Transmission Unit – the largest packet size the interface can handle.  |
| **RX-OK**    | Number of packets received without errors.                                      |
| **RX-ERR**   | Number of packets received with errors.                                         |
| **RX-DRP**   | Number of packets dropped due to errors or buffer overflow.                     |
| **RX-OVR**   | Number of packets that were received but had an overflow error.                 |
| **TX-OK**    | Number of packets transmitted successfully.                                     |
| **TX-ERR**   | Number of packets that could not be transmitted due to errors.                  |
| **TX-DRP**   | Number of packets dropped while being transmitted.                              |
| **TX-OVR**   | Number of packets that were transmitted but had an overflow error.             |
| **Flg**      | Flags associated with the interface, such as:                                   |
|              | - **B**: Broadcast support.                                                     |
|              | - **M**: Multicast support.                                                     |
|              | - **R**: Running. Indicates that the interface is actively transmitting data.   |
|              | - **U**: Up. The interface is enabled and can be used for communication.       |

### Key Flags:
- **Up**: The interface is **enabled** or **activated**. The system is aware of it and can use it, but it doesn't guarantee functionality or data transmission.
- **Running**: The interface is **fully operational** and actively participating in network communication, without errors.


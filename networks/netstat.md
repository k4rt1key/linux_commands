# Command : netstat 

Used for viewing network connections, routing tables, interface stats

```bash
netstat
netstat -a # for viewing active connection
netstat -l # for viewing open ports
netstat -s # for viewing network protocol wise stats
netstat -r # for viewing router table
netstat -p # for viewing process to port mapping
netstat -i # Displays network interface statistics, such as packets transmitted and received. useful for identifying issues like packet loss.

```

## OUTPUT 

```
Active Internet connections (servers and established)
Proto Recv-Q Send-Q Local Address           Foreign Address         State      
tcp        0      0 localhost:ipp           0.0.0.0:*               LISTEN     
tcp        0      0 localhost:domain        0.0.0.0:*               LISTEN     
tcp        0      0 kartikey:46916          52.123.173.232:https    ESTABLISHED
tcp        0      1 kartikey:51220          10.20.40.75:5405        SYN_SENT   
tcp        0      0 kartikey:42268          103.59.211.137:https    ESTABLISHED
tcp        0      0 kartikey:44722          bom12s19-in-f2.1e:https ESTABLISHED
```

Recv-Q = Number of bytes in receive queue
Send-Q = Number of bytes in send queue
Foreign Address = Ip of destination
State = State of connection

- LISTEN → Waiting for incoming connections.
- SYN_SENT → Sent connection request, awaiting response.
- SYN_RECEIVED → Received SYN, waiting for ACK.
- ESTABLISHED → Active connection, data transfer ongoing.
- FIN_WAIT_1 → Sent FIN, waiting for ACK or FIN from peer.
- FIN_WAIT_2 → Received ACK for FIN, waiting for peer’s FIN.
- CLOSE_WAIT → Received FIN, waiting for app to close socket.
- LAST_ACK → Sent FIN after receiving FIN, waiting for ACK.
- TIME_WAIT → Closed, waiting to ensure all packets are received.
- CLOSED → Connection fully terminated.

```
Active UNIX domain sockets (servers and established)
Proto RefCnt Flags       Type       State         I-Node   Path
unix  2      [ ]         DGRAM                    44584    /run/user/1000/systemd/notify
unix  2      [ ACC ]     STREAM     LISTENING     44587    /run/user/1000/systemd/private
unix  2      [ ACC ]     STREAM     LISTENING     44592    /run/user/1000/bus
unix  2      [ ACC ]     STREAM     LISTENING     40004    @/tmp/dbus-x2nIjwko
```


- UNIX domain sockets (UDS) are inter-process communication (IPC) mechanisms that allow processes on the same machine to communicate efficiently. Unlike network sockets (which use IP and ports), UDS use file paths in the filesystem.
- RefCnt → Number of processes using the socket.
- Flags →
  - [ ACC ] → Accepting connections (server socket).
  - [ ] → No special flags (datagram or connected socket).
- Type →
    - STREAM → Connection-oriented (like TCP).
    - DGRAM → Connectionless (like UDP).
- State →
    - LISTENING → Waiting for incoming connections.
    - CONNECTED → Actively communicating with another process.
- I-Node → Filesystem inode number for the socket.
- Path → The file path or abstract namespace used for the socket.

```bash
netstat -r
```

### OUTPUT 

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


Private ip vs link local ip
- Assigned manually or via DHCP.	v/s  Self-assigned when no DHCP server is available.
- Requires a Gateway?YES to communicate outside the local network.	vs No, direct communication within the same link.
- Not directly accessible, requires NAT to reach the internet. v/s	Never accessible on the internet, always local.


```bash
netstat -i
```

```
Kernel Interface table
Iface      MTU    RX-OK RX-ERR RX-DRP RX-OVR    TX-OK TX-ERR TX-DRP TX-OVR Flg
enp0s31f  1500        0      0      0 0             0      0      0      0 BMU
lo       65536    24619      0      0 0         24619      0      0      0 LRU
wlp0s20f  1500   882554      0  14711 0        204616      0      0      0 BMRU
```

# Summary of `netstat -i` Command

The `netstat -i` command displays the network interfaces and their statistics. Here's a breakdown of the columns and flags you might encounter:

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



### Explanation of Example:

- **enp0s31f**: This interface has no transmitted or received errors, and no dropped packets. It supports broadcasting and multicast.
- **lo**: The loopback interface, which has no errors and is used for local communication within the system.
- **wlp0s20f**: This Wi-Fi interface has received 882,554 packets, with 14,711 dropped, but no errors. It supports broadcasting, multicast, and is running.

### Key Points to Remember:
- **RX-OK** and **TX-OK** represent successful packet receptions and transmissions.
- **RX-ERR** and **TX-ERR** show the number of errors encountered during data transfer.
- **RX-DRP** and **TX-DRP** indicate dropped packets, which could be due to buffer overflow or network congestion.
- **Flags** like **Up** and **Running** indicate the status of the interface (whether it's enabled or actively transmitting data).


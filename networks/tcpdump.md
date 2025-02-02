# Tcpdump

- Similar as wireshark

```bash
tcpdump -vvv host kartikey and port 443 # Verbose : -vv
tcpdump -i [interface] 
```

### Output formats
```bash
12:23:24.704618 IP (tos 0x0, ttl 64, id 11588, offset 0, flags [DF], proto TCP (6), length 91)
    13.107.253.68.https > kartikey.55078: Flags [P.], cksum 0x4e22 (correct), seq 2494065144:2494065183, ack 721982099, win 204, options [nop,nop,TS val 624280566 ecr 3817517273], length 39
```

### Breakdown:

- **Timestamp**: `12:23:24.704618`
  - This shows the exact time when the packet was captured.

- **Packet Type**: `IP (tos 0x0, ttl 64, id 11588, offset 0, flags [DF], proto TCP (6), length 91)`
  - **TOS (Type of Service)**: `0x0` — This is the type of service, which is used for routing and prioritizing packets.
  - **TTL (Time To Live)**: `64` — The TTL value specifies the remaining hops (routers) the packet can make before being discarded.
  - **ID**: `11588` — A unique identifier for the packet used for reassembly if fragmented.
  - **Flags**: `[DF]` — "Don't Fragment" flag, indicating that the packet should not be fragmented during transmission.
  - **Protocol**: `TCP (6)` — The packet uses the TCP protocol (Protocol number 6).
  - **Length**: `91` — The total length of the IP packet in bytes.

- **Source IP and Port**: `13.107.253.68.https`
  - **Source IP**: `13.107.253.68` — The IP address of the machine that sent the packet.
  - **Source Port**: `https` (Port 443) — The port on the source machine (typically used for HTTPS traffic).

- **Destination IP and Port**: `kartikey.55078`
  - **Destination IP**: `kartikey` — This is your machine's IP address or hostname (where the packet is being sent to).
  - **Destination Port**: `55078` — This is the destination port on your machine (a high port number assigned dynamically).

- **Flags**: `Flags [P.]`
  - **[P.]** indicates the packet contains data and is part of an ongoing TCP connection. "P" stands for the PSH (Push) flag, which tells the receiving end to pass the data to the application layer immediately.

- **Checksum**: `cksum 0x4e22 (correct)`
  - This shows the checksum for error-checking. The checksum is correct, indicating no errors were detected in the packet.

- **Sequence Number**: `seq 2494065144:2494065183`
  - **Sequence Number**: `2494065144` — The starting sequence number of this packet's data.
  - The sequence number is used to order the packets in a TCP stream.

- **Acknowledgment Number**: `ack 721982099`
  - The acknowledgment number indicates the next expected sequence number the sender of the packet is expecting to receive. This is part of the handshake/acknowledgment mechanism in TCP.

- **Window Size**: `win 204`
  - The window size specifies how much data (in bytes) the receiving machine is willing to accept before sending an acknowledgment. It controls flow control in TCP.

- **Options**: `options [nop,nop,TS val 624280566 ecr 3817517273]`
  - **NOP**: No-Operation — A padding option.
  - **TS val 624280566 ecr 3817517273**: These are timestamps used for round-trip time measurements, part of the TCP options to optimize performance.

- **Length of Data**: `length 39`
  - The data portion of this packet is 39 bytes long.

---

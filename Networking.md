# Networking

## Packets

| Header | -- Payload -- |

IP Header

### OSI Layers and Encapsulation
```
Application
Presentation
Session
Transport
Network
Data Link
Physical
```
The entire **upper** protocol packet is the payload of the **lower** one.

## TCP/IP layers
```
Application
Transport
Network
Data Link
```

## Internet Protocol

### IPv4 Addresses
32-bit address

IP Address and Network Address (Bitwise AND with subnet mask)

CIDR notation

Host part (Bitwise AND with (NOT of subnet mask))

Network address = host part made all zeros

Broadcast address = host part made all ones

[Subnet Calculator](http://www.subnet-calculator.com)

### IPv6 Addresses
128-bit address

Loopback address = `::1/128`

IPv4 mapped addresses = `::FFFF:0:0/96`

IPv6 address can be split in half = network part + device part

First 48-bits for Internet global addressing

Next 16-bits are for defining subnets

Last 64-bits are for device interface IDs

#### Address Types and Scope
- Global Unicast Address - global addresses, reside in global internet
- Unique Local and Link Local - reside only in internal networks

#### Subnetting
There are prefixes (instead of subnet blocks)

E.g. `2001:1111:1234:1234::/64`

64-bits used for a prefix. Everything behind it can be used for hosts of the subnet.

[IPv6 subnet calculator](https://www.ultratools.com/tools/ipv6CIDRToRange)

## Routing
Happens at the Network layer, using IP addresses

Routing table with IP-to-interface binding and (cost) metric

`route print` on Windows

`ip route` or `route` in Linux
- To add a new route `ip route add <network/netmask> via <IP>`

`netstat -r` on macOS

## Link Layer Devices (Hubs/Switches) and Protocols
Happens at the Link layer, using MAC addresses

Forwarding table = Content Addressable Memory (CAM) table binds MAC addresses to interfaces

TTL determines how long an entry will stay in the forwarding table

### MAC Addresses
48-bit long hexadecimal

`ifconfig /all` on Windows

`ifconfig` on *nix

`ip add` on Linux

### ARP
When a host doesn't know the MAC address of the destination (only knows IP address)

ARP cache entries have a TTL

Check ARP cache
`arp -a` on Windows

`arp` on *nix

`ip neighbour` on Linux

### Hub v/s Switch
Hub has the same purpose (not same functionality) of a Switch. Dumb switch that 

## TCP & UDP
TCP - guarantees packet delivery (lower throughput) + connection oriented

UDP - no packet delivery guarantee (higher throughput) + connectionless

### Ports
Used to identify a network process on a machine.

#### Common Ports
| Port | Use |
| - | - |
| 21 | FTP |
| 115 | SFTP |
| 22 | SSH |
| 23 | Telnet |
| 80 | HTTP |
| 443 | HTTPS |
| 25 | SMTP |
| 110 | POP3 |
| 143 | IMAP |
| 3389 | RDP |
| 3306 | MySQL |
| 1433 | MS SQL Server |

#### netstat
To check the listening ports and current TCP connections

`netstat -ano` on Windows (or Sysinternals TCPView)

`netstat -tunp` on Linux

### TCP Three Way Handshake
1.  SYN flag + Client SEQ Number + 0 ACK Number
2. SYN & ACK flag + Server SEQ Number + (Client SEQ + 1) ACK Number
3. ACK flag + (Client SEQ + 1) Number + (Server SEQ + 1) ACK Number

Deviation from above usually means some filtering in place (IDS/IPS etc.)

## Firewalls and Network Defense

### Firewalls
Can **work on different layers** of OSI model

Packet filtering with rules. Doesn't inspect the payload.

### IDS
Inspects the application payload. Uses signatures.

1. Network IDS (NIDS) - inspect network traffic, usually placed on a router
2. Host IDS (HIDS) - monitor application logs, filesystem changes, OS changes

### IPS
Can drop malicious requests

### NAT and Masquerading
Single public IP, multiple private IPs

## DNS
Application Layer protocol

hostname -> IP

### Structure
TLD > Domain Name > Subdomain Name > Host Name

`members.elearnsecurity.com`
`members` = Host
`elearnsecurity` = Domain
`com` = TLD

## Wireshark

### Display Filters
`<ProtocolName>[.field] operand value]`
e.g. `ip.addr == 192.168.12.13`


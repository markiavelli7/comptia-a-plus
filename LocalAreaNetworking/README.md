# TCP/IP

10.11.12.13

Each one of the above sequences (10, .11, .12, .13) is an octet.

The IP address has to do two things:

1. Identify which LAN we are a part of
2. Give us a unique host ID

## An IP Address

- 4 Characters
- Numbers go from 0 - 255
- 3 Dots in between them
- Addresses never begin with a 0 or a 255

### IPs in the Ethernet Frame

With the inclusion of IPs, our Ethernet Frame will look something like this now:

_DESTINATION MAC_ => _SOURCE MAC_ => _DESTINATION IP_ => _SOURCE IP_ => _DATA_ => _FCS_

## The reason why we can't put a 0 on the end of an IP is that it signifies that we are talking about a NETWORK ID:

10.11.12.0

The NETWORK ID identifies an entire LAN.

## Subnet Mask

255.255.255.0

Wherever we see a 255 in a subnet mask, the numbers have to be the same. If we see a 0, the numbers can be different.

When two computers on the same LAN are trying to communicate, the source computer will look at the subnet mask. Using the subnet mask it can determine something very important: if the other computer is in its LAN. The computer figures this out by comparing its IP with the destination IP.

## Router

The router has its own IP address within a LAN (usually ending in .1). When a computer in a network sees that the IP address of the other computer does not belong to its LAN, it will send the request to the router. The router is the DEFAULT GATEWAY.

### Connecting a Computer to the Internet

1. Give it an IP address
2. Give it a subnet mask
3. Give it a default gateway

The subnet mask is only there to let our computer know if the request is a long distance call (WAN/internet) or a local call (LAN).

# Static IP Addresses

When we type in an IP address by hand, we are configuring a static IP address.

## Special IP Addresses

Class A - 1.0.0.0 - 126.0.0.0
Class B - 128.x.0.0 - 191.x.0.0
Class C - 192.x.x.0 - 223.x.x.0
Class D - 224.x.x.x
Class E - 240.x.x.x

Class D is a multicast address, used for presentations, etc
Class E is reserved

### Private IP Addresses

Class A - 10.x.x.x

Anytime we see a class A IP address that starts with 10, it is a private IP address.

Class B - 172.16.0.0 - 172.31.0.0

Class C - 192.168.0.0

If a router that is connected to the internet ever sees an IP address that begins with any of the private prefixes, it will erase the packet.

### Loopback

127.0.0.1

Refers to our own system, handy way to test our computer

# Network Address Translation (NAT)

Saves IP addresses.

With NAT, internal networks use private IP addresses and share a public address.

All gateway routers are NAT-enabled by default

Networks that use NAT are invisible to the public internet.

We still have an IP address on the WAN side of the router that is supplied to us by the Internet Service Provider (ISP). However, all of the addresses inside of our netwark are going to use a private IP address (192.168.5.0 etc).

When a computer with a private IP address wants to make a request to another computer outside of the network, the DEFAULT GATEWAY (router) takes off the private IP address (192.168.x.x) and inserts its own WAN address (legitimate public IP address from the ISP) into the packet. In the NAT, the router will keep track of which computer within its network sent the request and the IP address of the destination computer.

# Dynamic IP Addressing

## Dynamic Host Configuration Protocol (DHCP)

We connect our computers and something within the network will give us an IP address, subnet mask, etc. We call that a DHCP server.

Most of our home routers will also act as a DHCP server.

When a computer in the network boots up or a new computer is added to the network, it will want an IP address and start looking for a DHCP server.

The DHCP server will hear the computers call and hand them all of the IP address information: their IP address, subnet mask, and the default gateway server IP.

DHCP assignment is done automatically

## DHCP servers are computers within our LAN. Being a computer, there is a chance that it may be down one day.

It the DHCP server is down, most OSes have a fallback:

### Automatic Private IP Addressing (APIPA)

APIPA is a fallback in case we can't find a DHCP server.

By default, APIPA will always give a 169.254.x.x address.

In situations where communications within the LAN seem to work, but there is no internet connectivity, one of the first things to check is if the local computers have APIPA IP addresses. This will point to a problem with the DHCP server.

### Renewing IP Addresses

```bash
ipconfig /renew
```

ipconfig /renew will connect us to a DHCP server

ipconfig /release will disconnect us from a DHCP server

# IPv6

Use a 128 bit addressing scheme and hexadecimal notation.

8 groups separated by 7 colons.

aef0:0000:0000:0000:0000:0000:0000:a760

In an IPv6 address, we can get rid of leading 0's:

2001:0:0:1:0:0:0:8a2e

If we have three sets of 0 in a row, we can replace them with a colon:

2001:0:0:1::8a2e

Using IPv6, we will have a minimum of 2 IP addresses. One address is known as the **Link-local address**. The link-local address is distinct because it always starts with:

fe80:0000:0000:0000

The last half is automatically generated by our system itself.

The other address is the **Internet address (global unicast address)**. The internet address is brought down from the router itself.

Using IPv4, we only had one address, so the subnet mask is very important. But with IPv6 we have multiple addresses and instead of a subnet mask we have something called a **prefix**

# Port Numbers

Our web browser is a web client, web servers give us information. Everything on the internet is either a client or a server.

Our computer needs more than an IP address to keep track of the various requests and tasks. This is where ports come in.

**A port number is what gets us to the right application.** The IP address gets us to the right computer, the port number gets us to the right application.

Port numbers are numbered between 0-65535.

### There are 3 different kinds of port numbers:

- **Well-known ports (0-1023)**
- **Registered ports (1024 - 49151)**
- **Dynamic/Ephemeral ports (49152-65535)**

## Common Port Numbers

21 - FTP
22 - SSH
23 - TELNET
53 - DNS
80 - HTTP
110 - POP3
161/162 -SNMP
143 - IMAP
443 - HTTPS
3389 - RDP
137-139 - NETBIOS/NETBT
445 - SMB/CIFS
427 - SLP
548 - AFP
67/68 - DHCP
389 - LDAP

#### Just like we have a destination and source IP address, we are always going to have a destination and source port.

# Protocols

Nothing more than a set of rules that allow different systems to work together.

## Transmission Control Protocol/Internet Protocol (TCP/IP)

TCP/IP is two different protocols working together to help get the data between our systems.

TCP/IP is a connection based protocol and sends multiple packets

UDP is a connectionless protocol and sends multiple packets

ICMP is always a single packet (think ping)

## Protocol Data Unit (PDU)

We organize packets by protocol data units

TCP segment/UDP datagram

# Domain Name System (DNS)

We can statically configure DNS and still use DHCP for IP addressing

Have an alternative public DNS server in case our DNS server is down

Acts as a speed dialer that resolves a human readable address into an IP address.

DNS is like the contact list on our phone, but for the internet. DNS replaced something called the **Hosts file.**

**DNS Components**

- Root Servers - '.'

- First Level Domains - '.com, .edu, .gov'

- Second Level Domains - 'totalsem.com, google.com'

#### Fully Qualified Domain Name (FQDN)

Has a 256 character limit

All internet-connected hosts have a DNS server

## Working With DNS

DNS is provided by our DHCP server

#### Google's DNS Servers

8.8.8.8
8.8.4.4

If we think that we might have a DNS Server problem, we can statically set 8.8.8.8 or 8.8.4.4 as our secondary DNS server to verify that our local DNS server is down.

### Tools for Solving DNS problems

**nslookup**: built into most OSes

### Different Records that DNS Stores

- **A name**: www.xxxx.com and IP address
- **MX record**: used by mail servers
- **C name**: if there is more than one name for a particular IP address, it can give them different names

# Windows Naming

Windows naming is designed for LANs

When we install windows, we give the computer a Windows name

Every computer on our network needs a name. Windows naming uses **Netbios/netbt**

If we install a Windows system, it will either be a member of a Workgroup or an Active Directory Domain.

A Workgroup is the most basic type of system.

To use an Active Directory Domain, we need a Windows server. An ADD provides great security and very good central administration.

Homegroup doesn't really exist on current Windows OSes anymore, but were a Workgroup on steriods, with more security and automated organization.

# Routers

Devices that filter and forward traffic based on IP addresses. The magic tools we use to connect LANs.

### Routing Tables

Determines where to filter or forward IP packets

Tell the router where to send stuff

Every routing table has a default gateway where it sends all data unless otherwise specified

Yost/Rollover cable usually has an RJ45 on one end and a DB9 connector on the other end.

Some routers use web connections, some use console ports

# Basic Router Configuration

We can configure both the WAN and LAN connections in our router

Avoid default settings for basic configurations (IP, SSID, password, etc)

Don't create too large of a DHCP pool

DHCP reservations set aside IP addresses in the DHCP pool

# Advanced Router Configuration

### Quality of Service QoS

Gives control on network bandwidth by many different criteria

Toolset that allows us to meter how much bandwidth devices get based on IP address, MAC address, certain ports.

#### Universal Plug and Play (UPnP)

Makes our device more visible

#### Link Layer Discovery Protocol

Help with network device identification

Windows tool that is on by default

#### Simple Network Management Protocol (SNMP)

Powerful tool used by network administrators to not only identify switches, but to be able to see how much bandwidth is going through the switch. To not only know that there is a router, but have an idea of what the router is filtering right now.

# Virtual Local Area Network (VLAN)

A VLAN takes one physical switch and electronically turns it into two or more switches.

In order to create a VLAN, we need to be able to access the switch. Since switches only have MAC addresses, we want to give any switch that we are going to tweak an IP address, simply for access.

When we can add the IP address, we have a **Managed Switch**.

If we have a switch and we start plugging devices in and they can't talk too each other, there is a good chance that we have a VLAN configuration issue.

## Port Security

Firmware interfaces in switches also allow features such as port security.

# Network Troubleshooting

**No Connectivity**: Are you connected? If yes, check IP Addressing, static addresses can cause problems

**Limited Connectivity**: DHCP problems. Check for APIPA IP addresses

**Intermittennt Connectivity**: Some kind of problem with the cabling itself, whether this is interference

**Unavailable Resources**: Can we get to the system itself? If we can get to the system, then there may be a problem with the resource itself.

**Slow Transfer Speeds**: Fire up task manager and see how hard our network card is being used. Use QoS systems to prioritize tasks/systems.

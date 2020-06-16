# Beyond the LAN

### LAN

Group of local computers that are all hooked together to one switch in such a way that they can easily communicate with each other. A LAN is distinct in that all of the computers within the network are going to share an identical network ID.

### WAN

Interconnecting LANs with routers. Using one or more routers to connect the LANs. Each WAN has a unique network ID.

### Metropolitan Area Network (MAN)

If we spread a WAN out across an entire city, we get a MAN.

### Internet

When we connect all of the LANs across the entire world, we get the internet.

### Personal Area Network (PAN)

Two and only two devices connected together with Bluetooth. Point-to-point connection.

# Internet Tiers

**Tier 1**: Provide internet to very large customers. There are a handful of competitors that create **Peering Agreements** to provide full coverage across North America. The centers where the competitors interconnect their networks are called **Network Operations Centers (NOCs)**.

**Tier 2**: Entities that aren't as big as Tier 1 providers, but they do have a fairly good coverage area. Tier 2's do not have Peering Agreements with the Tier 1 providers, they have to pay for their internet just like us.

**Tier 3**: Internet Service Providers (ISPs). Make their money by selling internet to corporations and individuals. No peering agreements, they pay for internet from Tier 1 and Tier 2 companies.

# Dial-up Connections

## Plain Old Telephone Service (POTS), Public Switched Telephone Network (PSTN)

Dial-up plugs RJ-11 connectors to the phone system

Modems convert analog POTS to digital COM port connections

Modems connect to other modems using a phone number

Landlines - we need telephone service.

We use a modem to connect the phone line to our system.

Then we have a **Comport** in our system that recognizes different serial ports.

In order to make an internet connection, we have to create a connection between our modem and another modem (usually from a ISP). We dial in and connect.

**Max out at 58Kbps**

## Integrated Services Digital (ISDN)

The first time that we started to move into the digital world. Completely digital line.

# Broadband Connection

The typical way that we connect. Cables, DSL, Wireless, and Satellite.

**Broadband is an always on connection**

## Digital Subscriber Line (DSL)

One of the earliest versions of broadband and it worked because it piggybacked on top of telephone lines to give us a digital service. DSL came in two forms:

**Asymmetric DSL (ADSL)**: Our upload speed was much slower than our download speed

**Symmetric DSL (SDSL)**: Our upload and download speeds are exactly the same

When setting up a DSL network, it is important to set up our routers into **Point-to-Point Protocol Over Ethernet (PPPoE)**.

## Cable

We have an incoming F-Type connection to our cable, then we have an Ethernet out port that goes to our router.

Uses a protocol called **Data Over Cable Service Interface Specification (DOCSIS)**. DOCSIS is pretty similar to ethernet in that it has MAC addresses.

## Satellite

The only downside to satellite is latency

## 802.11 Service Providers

Proprietary, uses ranges outside of the 802.11 standard

### Modem

This is a broad term that got carried over from dial-up. Dial-up is the only true modem. The other devices are really **terminal adapters.**

# Firewalls and Servers

All internet connections require a client and a server

One of the primary functions of firewalls is to block ports

Client and server networks use firewalls

Firewalls block ports on an incoming vs. outgoing concept

Servers must not block incoming ports on the ports to which they listen

Lets say that we are using our browser to connect through the internet to a server.

A HTTP browser uses port 80 on our computer as the outgoing port. The server computer will have a firewall that will allow incoming connections to port 80. Our router will also have a firewall that will allow outgoing connections to port 80, but block any incoming port 80 connections.

# File Transfer Protocol (FTP)

**Uses Port 21**

Every web browser is an FTP client.

If we want to do heavy duty FTP work, we need a more robust client, something like **FileZilla**.

### Passive Mode

Everything is done on port 21.

### Active Mode

When we send a communication out on port 21, the server will send communications back on port 20. **Servers don't like this and will block the connection**

**Active mode is about 5x faster than passive mode.** The only problem is that any good router will block a request from an uninitiated port (in this case port 20). To get around this, most routers have something called **Port Triggering**.

# E-Mail

**Simple Mail Transfer Protocol (SMTP)** - Port 25
**Post Office Protocol (POP3)** - Port 110
**Internet Message Access Protocol (IMAP)** - Port 143

**SMTP** is the protocol that we use to send our mail up to an SMTP server. So we have to configure an SMTP server.

**POP3 and IMAP** bring email down from the server to our client. POP3 is very simplistic. It works great but we have to set up all of our own folders on the client itself. IMAP copies all of the folders on the server and sends them down to the client.

Latest versions are **POP3** and **IMAP4**.

# Proxy Servers

Acts as a go-between between a client and a server.

Proxy servers provide firewalling, check for malware, ban bad URLs.

Applications must know the address of the proxy server.

Extremely popular in schools.

Application specific. If we want to proxy web pages, we have to go into our web browsers and make some changes.

Proxy servers can do caching.

# Virtual Private Networks (VPNs)

Use the Internet to create a private connection to a remote network.

We need a VPN client program that connects to a VPN server at the remote network.

The VPN client needs to know the IP address of the VPN server to make the connection.

# Internet of Things (IoT)

**802.11**
**ZigBee** runs on the 2.4GHz band and doesn't have a whole lot of bandwidth because it doesn't need it
**Z-Wave** 900MHz

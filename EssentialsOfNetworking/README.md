# Essentials of Networking

## Ethernet

We can send data in discrete chunks of 1500 bytes.

Each one of these chunks of 1500 bytes is called a frame.

## How Do We Uniquely Identify Every Computer on the Network?

## MAC (Media Access Control) address

A MAC address is a 48 bit address that is always manifested as 12 hexadecimal characters.

The first 6 of 12 hexadecimal characters are the OEM ID.

## Adding to the Frame

_DESTINATION MAC ADDRESS_ => _SOURCE MAC ADDRESS_ => _DATA_ => _FCS_

### Frame Check Sequence (FCS)

The Frame Check Sequence helps ensure that the data arrived in good order.

# Hubs vs Switches

A Hub is a repeater that takes the signal that comes in and creates a new copy for every connected device. Everybody gets the conversation. The computers will read the MAC address associated with the frame, and if it's not for them, they will discard it.

## Hubs repeat all traffic on the LAN to all nodes

A Switch, when connected will begin to collect MAC addresses. The switch will keep track of the MAC addresses of all of the connected computers. Because the switch knows all of the MAC addresses of the connected computers, when a frame comes in, the switch will look at the destination MAC address and send the frame there. A switch is a smart repeater that only sends the data to the destination based on the MAC address.

## Switches filter traffic based on the MAC address

## Switches provide full bandwidth for all nodes

# Hexadecimal

Hexadecimal is an easy shorthand used to talk about long strings of binary.

Hexadecimal is a base 16 numbering system.

# WANs and Routers

The Internet standard says that we will never put more than 1024 connected computers on one LAN.

30 - 40 computers is an industry standard for a local area network.

### A Wide Area Network (WAN) is just a whole bunch of LANs connected together.

## Router

Routers are sensitive to different local area networks and can differentiate between not only different computers, but different LANs.

The MAC address allows us to get information to different computers within a LAN, but we need something different that allows us to identify local area networks.

## Logical Addressing

A dynamic value that identifies a particular LAN.

## IP Addressing

192.168.4.100

Every device inside of our LAN gets a unique address, which in this example has the first three sequences as:

192.168.4.x

The last number has to be unique and different.

The router is a member of network as well. By convention, we tend to give it the .1 address, ie 192.168.4.1

If any of our devices want to talk to another device that doesn't start with 192.168.4, they have to send it to the router.

The router is the **DEFAULT GATEWAY**.

in addition to the 192.168.4.1 IP address, the router holds another IP address, for example 23.11.4.1. The second IP address is not a part of LAN, it belongs to a different network entirely.

The reason why most people have never had to type in the 192.168.4.x numbers is because of DHCP, DHCP automatically handles all of this for us.

### Every computer has two very different types of addresses, one is the physical address (MAC address), the other one is a logical address, called an IP address. The physical address is used within a LAN, the logical address is used within a WAN.

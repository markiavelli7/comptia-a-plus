# Wireless Network Hardware

## Wireless Access Point (WAP)

A wireless access point is nothing more than a bridge between an Ethernet network and a wireless 802.11 network.

A true WAP is going to only have one ethernet connection. Home routers have a WAP built in.

## Infrastructure Mode

If we have a WAP (or multiple WAPs), we are in infrastructure mode.

If we have a WAP, we are going to have a wireless network card of some kind.

## Ad Hoc Mode

There are no WAPs, a defined system will act as the access point for all of the other systems.

## Wireless Network Card

In a laptop, the antenna for the wireless connection is in the monitor itself

### Antennas

Omni-Directional - radiation pattern looks like a big fuzzy ball. **Dipole** has two attennas pointing in opposing directions, this creates a good signal

Patch - Flat looking, the signal is a big fuzzy ball, but only half of one

Highly Directional - **Yagi**, really good for shooting long distances

# Wi-Fi Standards

802.11 uses two bands: the ISM 2.4Ghz and 5 Ghz bands

802.11 also uses premade channels

Original Standard - 1Mbps

A band is just a range of radio frequencies.

In the 802.11 2.4GHz range, there are 14 different channels. Each channel takes a different piece of the band. We can tune our different WAPs so that different users don't step on each others channels.

On the 5GHz band, the numbering is a lot more complicated.

### 802.11a

54Mbps - 5GHz

### 802.11b

11Mbps - 2.4GHz

### 802.11g

54Mbps - 2.4GHz

### 802.11n (Wi-Fi 4)

100Mbps - 2.4GHz/5GHz

### 802.11ac (Wi-Fi 5)

1.3Gbps - 2.4GHz/5GHz
Includes Multi-user MIMO. Instead of just having one client that we can zoom in on, it lets us focus the signal on multiple clients

### Multiple In/Multiple Out (MIMO)

Allows a single WAP to use multiple antennas to change its signal to zero in on a single device.

# Basic WAP Setup

A site survey shows available channels in an ISM band

We must create a service set identifier (SSID)

Most WAPs support multiple SSIDs

We can hide SSID broadcasts

We can define extensions to support, channels, and channel width

## Service Set Identifier (SSID)

In order for a wireless access point to provide the ability for individual wireless clients to connect to it, we have to create the SSID.

### Hiding/Disabling the SSID Broadcast

Comptia recommends setting up the network and then turning off the SSID broadcast. **This will only stop the honest people**

# Connecting to a Wi-Fi Network

Most operating systems have an option to remember the network. This can be handy until something like the password changes. Then we will get connection errors.

If we have trouble with a remembered network, the first thing to do is to forget the network and then try to reconnect.

### Issues with Connecting to an SSID

1. Network Interface Controller (NIC) is configured as a DHCP client. We try to connect to a network and it says that we are connected, but we get an APIPA address 169.254. That is a clue that we have a bad password.

2. Passwords can change, if we can't access a network that we have been able to in the past, forget the network and try to rejoin.

3. Set wireless NIC to a static IP Address. Though it is uncommon, we can set the wireless NIC with logical addressing, manual Default Gateway, IP, and subnet mask. It will look like a wireless issue but really be an IP configuration issue.

# It's One Big Mesh

## Wireless Mesh Network (WMN)

A great wireless solution for SOHO environments.

Mesh networks use their own encryption.

Ad Hoc mode but on steriods, very easy to setup.

We have one base station that is connected to the actual network itself.

Then we can start placing external beacon devices that connect to the base station to extend coverage.

# Beyond Wi-Fi

## Radio Frequency Identifiaction (RFID)

RFID manifests as a tiny little sticker. The sticker is actually a radio that usually stores a few hundred bits of information.

Then there are RFID readers that use their energy to power up these little stickers, and then these little stickers have enough energy to transmit back.

RFID is used mostly in industrial applications as well as **Near Field Communication (NFC)**. We see NFC in the real world with Tap-to-Print or Tap-to-Pay devices. We see this a lot with smartphones. **NFC is RFID**.

## Bluetooth

The biggest difference between Bluetooth and 802.11 is that Bluetooth is designed to connect two devices, and **only two devices together at one time.** This connection is called a **Personal Area Network (PAN)**.

### Bluetooth Classes

**Class 1, 100mW, 100 meter range**

**Class 2, 2.5mW, 10 meter range**

**Class 3, 1 mW, 1 meter range**

## Troubleshooting Wireless Connections

**No Connectivity**: Make sure the SSID exists. If the problem is a connection that is very weak, there is probably a low radio frequency signal. If that's the case, if our WAP has antennas, we will want to look at them. With dipole antennas, they usually work best when they are pointing straight up and down. Another option is that someone may have turned off SSID broadcasting.

**Limited Connectivity**: This is interference in a lot of cases. The solution can be finding the interference and pushing that stuff out of the way.

**Intermittent Connectivity**: Low RF signals. Too many people on a wireless network. If there are too many people, the only solution to accomadate everybody is more WAPs. If we want certain computers to have good signals regardless, we will want to set up QoS.

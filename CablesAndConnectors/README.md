# Ethernet

Ethernet defines the type of cabling and connectors that we use.

## Other Methods

### DOCSIS - used for cable modems

## Types of Ethernet

- 10BaseT (10Mbps baseband twisted pair)
- 1000BaseT (1000Mbps baseband twisted pair)
- 10GbBaseT (10Gbps baseband twisted pair)

## Types of Cable

### Coaxial

Cables are axial. Center is a conductor, surrounded by an insulator, and then the outer cladding which is a signal tool as well.

**RG Ratings**

- RG-58: Very thin cable that used to be used in the networking sector. Used a special connector called BNC Connector.

- RG-59, RG-6: Used in the cabling world for video and for networking. These cables use threaded F-type connectors

### Twisted Pair

The predominantly used type of cable.

**Unshielded Twisted Pair (UTP)**

The twists help propogate the single better and in general have a max length of 100 metres.

Telephone uses a 4 contact **RJ-11** connector

Networking uses an 8 contact **RJ-45** connector

**Shielded Twisted Pair (STP)**

Resistant to electrical interference from lighting, electric motors, etc.

### Fiber Optic

Two ways to propogate the light signal:

- Multimode: uses LEDs to send the signal
- Singlemode: uses Lasers to send the signal

When working with Fiber, one single wire usually only sends or receives, **so it is very common to see pairs.**

## Twisted Pair Cat (category) Ratings

### Cat 5: 100Mbps

### Cat 5e: 1Gbps

### Cat 6: 1Gbps up to 100m, 10 Gbps up to 55m

### Cat 6a: 10Gbps at 100m segments

### Plenum Ratings

- PVC (non plenum)
- Plenum Rating (More resistant to fire)
- Riser Rating

# Crimping Cables

Two Standards:

## TIA 568A

1. Green/White
2. Green
3. Orange/White
4. Blue
5. Blue/White
6. Orange
7. Brown/White
8. Brown

## TIA 568B

1. Orange/White
2. Orange
3. Green/White
4. Blue
5. Blue/White
6. Green
7. Brown/White
8. Brown

If it starts with a B (Brown or Blue), it stays in the same place.

Looking straight on at the connector with the tab at the bottom, **pin 1 is on the right.**

## To stay within the cat ratings, the distance between the crimp and the end of the twisted pair has to be less than half an inch.

**Straight through** cables have the same wiring type on each end.

**Crossover** cables will use one side as 568A and one side as 568B and can be used for computer to computer communication without a switch.

# Structured Cabling

Starts in a closet or room that contains the Main Distribution Frame (MDF) or Intermediate Distribution Frame (IDF).

On the rack, 19" is a very common width

## Patch Panel

The individual cables that make up horizontal runs terminate into a patch panel.

Patch cables act as the interconnection between the patch panel and our switches.

**According to TIA rules, the longest horizontal run we can have is 90m.** The reason why it is 90m when Ethernet allows for 100m is that we are compensating for the patch cables.

## 110 Punchdown tool lets us connect to our horizontal runs into the back of the patch panel.

### TDR is used for testing the length and integrity of runs.

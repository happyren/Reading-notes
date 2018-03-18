# Internet Technology

> Internet Technology Note sheet

## Contents

- [OSI model](#osi-model)
- [Why Internet](#why-internet)
- [Lecture Notes](#lecture-notes)

## Why Internet

### For business

Sharing data amongst employees are necessary. At a point of resource sharing, the management would like to connect all the private employee computers together. It normally deployed in **client-server model**.

> Client-server model: client send a message to server, then server process and send message back to client. ![Client-Server](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Client-server-model.svg/1200px-Client-server-model.svg.png)

Setting up computer network in business normally has goals:

1. Connect employee and make easy for resource sharing.

2. Providing powerful tools for employee to communicate.

3. Doing business electronically, especially with customers.

### Home Application

The biggest reason for home to buy personal computer is to connect to the Internet. And the connection is often processed in peer-to-peer model.

> Peer-to-peer model: individuals form a loose group and make communication within the group.![Peer-to-peer](https://geekipedia.info/wp-content/uploads/peer-to-peer-network.png)

Home internet is often setup due to:

1. Let home user connect to other computers.

2. Person-to-person communication, using social media or create content jointly like wikipedia.

3. Electronic commerce, online shopping, amazon, e-flea market.

4. Entertainment like online games.

5. Ubiquitous computing in Internet of Things, RFID.

### Mobile users

Cellular, WiFi, GPS, etc.

## Harware Technology

Generally, there are two type transmission technology in daily usage.

> Broadcast link: Packet coubld be sent by any machine and recieved by all the others. Machine only process packets intended to be received but drop those do not.

> Multicasting: packets are transmitted to subset of machines.

> Point-to-point link: Packet is sent by exactly one sender and received by exactly one receiver.

And the technology could also be categorized by scale:
| Distance | Density | Example |
| ------------------ |:-------:|:-------:|
| 1 m | Square Meter | Personal Area Network|
| 10 m | Room | Local Area Network |
| 100m | Building | LAN |
| 1 km | Campus | LAN |
| 10 km | City | Metropolitan Network |
| 100 km | Country | Wide Area Network |
| 1000 km | Continent | WAN |
| 10,000 km | Planet | Internet |

### PAN

Let devices communicates over a range of a person. For example, computer with monitor, keyboard, and mice, cable or bluetooth.

### LAN

Privately owned network operates within and nearby an office, home, or building , or factory. It requires Access Point, or wireless router, or base station. Protocol _IEEE 802.11_ is widely known as **WiFi**, while _IEEE 802.3_ is widely known as **Ethernet**. Logical divided LAN is also possible, which is Virtual LAN or VLAN.

In LAN, since the size is restricted, we could know the worst case scenario in advance. And for wired LAN conncetion using copper wires and optical fiber, the connection speed often at 100Mbps to 1Gbps, the latest reach 10Gbps. **Wired is overrun wireless in every way**.

- Static allocation: it divide channel into time slot, a machine can only broadcast during its slot, which caused channel capacity waste when a machine has nothing to say.

- Dynamic allocation: Centralized allocation would have a central entity which determines using an algorithm to decide which packet goes next, where the decentralized allocation doesn't have that central entity but using each machine to decide when to send the packet.

### MAN

MAN is firstly using by television channels, to distribute TV to subs, then it is found the cable could carry more channels, so Internet is also included.

### WAN

WAN spans large geo area, it consists of hosts and communication subnet, which requires transmission cable and switch elements. Compares to LAN, it separates communication and application for easy deployment. It utilizes multiple network technologies. And its subnet could connect to not only individual computers but also LANs.

Subnets could also be or not to be a Internet Subnet, and the service providers could vary for a **Network Service Provider** to **Internet Service Provider**.

> The method IPS choosing path called routing, choosing destination called forwarding.


## OSI model

OSI model comes from top to bottom, from the layer closest to user (Which is [Application layer](#application-layer)), to the layer wired into the network (which is [Physical layer](#physical-layer)).

### Application layer

This is the one that the **user actually interacting with**, like safari, chrome, or outlook application.

### Presentation layer

This is the one that **operating system is on**, information user input on application layer will be sent to presentation layer to the operating system to be further processed.

### Session layer

This one deals with the communication session between two computers. **It creates session with the web server which user would like to get data from**

### Transport layer

This layer decides the data size of one transmission.

### Network layer

The router operates on this layer. Assign IP address to a certain MAC address or a certain NIC.

### Data Link layer

Switch operates on this layer. Provides data transmission guide to packets.(This could be exploit with [ARP spoofing](https://en.wikipedia.org/wiki/ARP_spoofing).)

### Physical layer

All physical stuff connect the computers together. Most of network problem comes in this layer.

- cable disconnect
- cable misconnect

## Lecture Notes

### Link Model

consider with Bandwidth and Transfer Rate. Delay is always considered as the delay experienced by the first bit.

> Transfer delay: T-delay = Message length / Transfer Rate
> Propogation delay: P-delay = Channel length / Signal Speed
> Message Latency: ML = T-delay + M-delay

### Communication type

## Physical Layer

Firstly, using electronics cannot generates actual digital signal directly, because it exists break point, which violates the natural law of electricity. So instead, digital signal is decomposed into different possible signals, which is harmonic signal (sin and cos) with different frequency.

From the actual transmission, some frequency of signal may be attenuated, so there exist a cutoff frequency that defines how many frequencies are actually useful while transmitting, and from the lowest frequency to the highest frequency of the signal components are called bandwidth.

There could be baseband and passband, however, it is irrelevant with bandwidth, using baseband and passband, signals with different bandwidth could actually share the same channel by multiplexing.

And with higher bandwidth, a more accurate frequency could be reproduced by receiver, hence more bits could be transfered at once, hence higher bandwidth means higher bit rate.

> The first harmonic is portraited as a 8bits chunk transmit on a b bits/sec data rate, hence the first harmonic freq is 1/8/b Hz = b/8 Hz.

Bandwidth has different definition in terms of electrical (Hz) and CS (bits/sec). Bandwidth in CS means the maximum data rate let b/8 < Bandwidth (Hz).

### Nyquist Theorem -- Maximum Data Rate of a channel

For bandwidth B, the sampling rate should be at least 2B to reconstruct the original signal and more than 2B is pointless due to the fact that the higher frequency is filtered out by the low pass filter using to limit the bandwidth.

> Nyquist theorem gives noiseless channel: Max(Data Rate) = 2BlogV; Shannon theorem gives noisy channel: Max(Data Rate) = BlogS/N, or if the S/N is in dB, Max(Data Rate) = B*dB/3.

### Guided media

#### Magnetic media

Write data into magnetic media, aka DVD, physically transmitted them to the destination.

> This method is very cost effective! Used for applications requires high bandwidth and cost per bit, and don't request low delay.

#### Twisted Pairs

Two copper wires twisted into one, forming an attena, cancelling out wire radiates, transmitting signal using the voltage difference between two wire, hence less affected by noise.

> It could achieve several megabits/sec, it has low cost and can go online.

There are some topologies:

1. Links can be used in both direction at the same time is called full-duplex.

2. Links can be used in bi-direction but only one at a time is called half-duplex.

3. Links can only be used in one direction is called simplex.

#### Coaxial cable

![Coaxial Cable](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f4/Coaxial_cable_cutaway.svg/2000px-Coaxial_cable_cutaway.svg.png)



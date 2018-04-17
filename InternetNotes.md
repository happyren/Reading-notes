# Internet Technology

> Internet Technology Note sheet, based on _Computer Network Pearson.2011_

## Contents

- [Introduction To Internet](#introduction)
- [Hybrid Model(Major Chapters)](#hybrid-model)

## Introduction

- [Internet Usage](#internet-usage)
- [Hardware Technology](#hardware-technology)
- [Software Technology](#software-technology)
- [Reference Model](#reference-model)

### Internet Usage

#### For business

Sharing data amongst employees are necessary. At a point of resource sharing, the management would like to connect all the private employee computers together. It normally deployed in **client-server model**.

> Client-server model: client send a message to server, then server process and send message back to client. ![Client-Server](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Client-server-model.svg/1200px-Client-server-model.svg.png)

Setting up computer network in business normally has goals:

1. Connect employee and make easy for resource sharing.

2. Providing powerful tools for employee to communicate.

3. Doing business electronically, especially with customers.

#### Home Application

The biggest reason for home to buy personal computer is to connect to the Internet. And the connection is often processed in peer-to-peer model.

> Peer-to-peer model: individuals form a loose group and make communication within the group.![Peer-to-peer](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/P2P-network.svg/2000px-P2P-network.svg.png)

Home internet is often setup due to:

1. Let home user connect to other computers.

2. Person-to-person communication, using social media or create content jointly like wikipedia.

3. Electronic commerce, online shopping, amazon, e-flea market.

4. Entertainment like online games.

5. Ubiquitous computing in Internet of Things, RFID.

#### Mobile users

Cellular, WiFi, GPS, etc.

### Harware Technology

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

#### PAN

Let devices communicates over a range of a person. For example, computer with monitor, keyboard, and mice, cable or bluetooth.

#### LAN

Privately owned network operates within and nearby an office, home, or building , or factory. It requires Access Point, or wireless router, or base station. Protocol _IEEE 802.11_ is widely known as **WiFi**, while _IEEE 802.3_ is widely known as **Ethernet**. Logical divided LAN is also possible, which is Virtual LAN or VLAN.

In LAN, since the size is restricted, we could know the worst case scenario in advance. And for wired LAN conncetion using copper wires and optical fiber, the connection speed often at 100Mbps to 1Gbps, the latest reach 10Gbps. **Wired is overrun wireless in every way**.

- Static allocation: it divide channel into time slot, a machine can only broadcast during its slot, which caused channel capacity waste when a machine has nothing to say.

- Dynamic allocation: Centralized allocation would have a central entity which determines using an algorithm to decide which packet goes next, where the decentralized allocation doesn't have that central entity but using each machine to decide when to send the packet.

#### MAN

MAN is firstly using by television channels, to distribute TV to subs, then it is found the cable could carry more channels, so Internet is also included.

#### WAN

WAN spans large geo area, it consists of hosts and communication subnet, which requires transmission cable and switch elements. Compares to LAN, it separates communication and application for easy deployment. It utilizes multiple network technologies. And its subnet could connect to not only individual computers but also LANs.

Subnets could also be or not to be a Internet Subnet, and the service providers could vary for a **Network Service Provider** to **Internet Service Provider**.

> The method IPS choosing path called routing, choosing destination called forwarding.

#### Network Devices

| Devices | Usage |
| --- | :---: |
| Repeater | Regenerates the signal to keep transmission strength|
| Hub | A multiport repeater |
| Bridge | On Data-Link Layer, filtering contents by reading MAC, connect 2 devices|
| Switch | Multiport Bridge with buffer |
| Router | Network Layer device, like switch, but can read IP address |
| Gateway | a passage to connect two networks together with both using different models |
| Access Point | Providing Wireless Connection for devices to Ethernet network |

### Software Technology

* [Protocol Hierarchy](#protocol-hierarchy)
* [Design Issues](#design-issues)
* [CO vs CL](#co-vs-cl-interms-of-services)
* [Service Primitives](#service-primitives)
* [Services to Protocols](#services-to-protocols)

#### Protocol Hierarchy

**Protocol** is an agreement between peers on how communication is proceed.

Actual data transmission is proceed on Physical Layer.

Between each pair of adjacent layers, there exist a interface, where lower layer provides premitive operations and services to upper layer.

Interface and layers should be properly designed, meet the _PoLP_, any change to the lower layer should not be noticed by the upper layer.

Protocol stack is the list of protocols used in different layers, one per layer.

#### Design Issues

1. Reliability: error detection, error correction, routing(path finding).

2. Network evolution: protocol layering, addressing, internetworking, model scalability.

3. Resource allocation: Statistical multiplexing, flow control, congestion, QoS.

4. Security: confidentiality, authentication, integrity.

#### CO vs CL (Interms of services)

CO is modeled after telephone system, CL is modeled after postal system.

> Store-and-forward switching: intermediate node receive the whole message, then send it.

> Cut-through switching: onward transmission starts before the message is fully received.

| CO or CL | Services | Example |
| --- | :---: | :---: |
| CO | Reliable message stream | Sequence of pages |
| CO | Reliable byte stream | Movie download |
| CO | Unreliable connection | Voice of IP |
| CL | Unreliable datagram | Electronic junk mail |
| CL | Acknowledged datagram | Text messaging |
| CL | Request-reply | Database query |

#### Service Primitives

| Primitive | Meaning |
| --- | :---: |
| LISTEN | Block waiting for an incoming connection |
| CONNECT | Establish a connection with a waiting peer |
| ACCEPT | Accept an incoming connection from a peer |
| RECEIVE | Block waiting for an incoming message |
| SEND | Send a message to the peer |
| DISCONNECT | Terminate the connection |

LISTEN, CONNECT, ACCEPT could be explained by 3-way handshake.

RECEIVE and SEND could be explained by HTTP transmission.

DISCONNECT could be explained by 2 pairs of DISCONNECT and ACK.

#### Services to Protocols

Service is not protocol, **service** is premitive operations a lower layer provides to its upper layer; **protocol** is the agreement between two communication peer on how communication is proceed.

### Reference Model

* [OSI Model](#osi-model)
* [TCP/IP Model](#tcp-ip-model)
* [Hybrid Model](#hybrid-model)

**Reference Models** are essentially architecture of networks, OSI(Open Systems Interconnection) is a good model, very general and still valid; TCP/IP its model is not of much use, but its protocols are still widely used.

#### OSI Model



#### TCP/IP Model

#### Hybrid Model

Hybrid model comes from top to bottom, from the layer closest to user (Which is [Application layer](#application-layer)), to the layer wired into the network (which is [Physical layer](#physical-layer)).

- Application layer

This is the one that the **user actually interacting with**, like safari, chrome, or outlook application.


- Transport layer

This layer decides the data size of one transmission.

- [Network layer(Unfinished Reading)](#network-layer)

The router operates on this layer. Assign IP address to a certain MAC address or a certain NIC.

- [Media Access Control Sublayer(Readings on example networks are unfinished)](#media-access-control-sublayer)

One of the sublayer of Data-Link Layer(the other one is logic link control), in charge of assignment of the MAC address.

- [Data Link layer](#data-link-layer)

Switch operates on this layer. Provides data transmission guide to packets.(This could be exploit with [ARP spoofing](https://en.wikipedia.org/wiki/ARP_spoofing).)

- [Physical Layer](#physical-layer)

All physical stuff connect the computers together. Most of network problem comes in this layer.

- cable disconnect
- cable misconnect

## Physical Layer

- [Nyquist Theorem](#nyquist-theorem-maximum-data-rate-of-a-channel)
- [Guided Media](#guided-media)
- [Unguided Media](#unguided-media)

Firstly, using electronics cannot generates actual digital signal directly, because it exists break point, which violates the natural law of electricity. So instead, digital signal is decomposed into different possible signals, which is harmonic signal (sin and cos) with different frequency.

From the actual transmission, some frequency of signal may be attenuated, so there exist a cutoff frequency that defines how many frequencies are actually useful while transmitting, and from the lowest frequency to the highest frequency of the signal components are called bandwidth.

There could be baseband and passband, however, it is irrelevant with bandwidth, using baseband and passband, signals with different bandwidth could actually share the same channel by multiplexing.

And with higher bandwidth, a more accurate frequency could be reproduced by receiver, hence more bits could be transfered at once, hence higher bandwidth means higher bit rate.

> The first harmonic is portraited as a 8bits chunk transmit on a b bits/sec data rate, hence the first harmonic freq is 1/8/b Hz = b/8 Hz.

Bandwidth has different definition in terms of electrical (Hz) and CS (bits/sec). Bandwidth in CS means the maximum data rate let b/8 < Bandwidth (Hz).

### Nyquist Theorem -- Maximum Data Rate of a channel

For bandwidth B, the sampling rate should be at least 2B to reconstruct the original signal and more than 2B is pointless due to the fact that the higher frequency is filtered out by the low pass filter using to limit the bandwidth.

> Nyquist theorem gives noiseless channel: Max(Data Rate) = 2BlogV; Shannon theorem gives noisy channel: Max(Data Rate) = BlogS/N, or if the S/N is in dB, Max(Data Rate) = B\*dB/3.

### Guided media

#### Magnetic media

Write data into magnetic media, aka DVD, physically transmitted them to the destination.

> This method is very cost effective! Used for applications requires high bandwidth and cost per bit, and don't request low delay.

#### Twisted Pairs

Two copper wires twisted into one, forming an attena, cancelling out wire radiates, transmitting signal using the voltage difference between two wire, hence less affected by noise, examples could be telephone and ADSL.

> It could achieve several megabits/sec, it has low cost and can go online.

There are some topologies:

1. Links can be used in both direction at the same time is called **full-duplex**.

2. Links can be used in bi-direction but only one at a time is called **half-duplex**.

3. Links can only be used in one direction is called **simplex**.

#### Coaxial cable

![Coaxial Cable](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f4/Coaxial_cable_cutaway.svg/2000px-Coaxial_cable_cutaway.svg.png)

It is better sheilded hence run on higher bandwidth with longer range.

50ohm one is normally used for digital transmission, while 75ohm one is normally used for analog transmission and TV signals(historical reason: early antennas had 300ohm impedance with 4:1 impedance-matching transformers.)

> It has high bandwidth and good noise immunity, but gradually replaced by optic fiber and long-haul routes.

#### Power lines

Initially used by power company for remote metering, now reused both in home as LAN and outside home as broadband Internet connection.(Mostly in home)

Difficulties:

1. Wiring normally setup for 50-60Hz electricity and will attenuate high freq signals.

2. Without careful twisting the twisted pairs, the wire will act like an antenna.

> Despite its disadvantage on transmitting high freq signal and bad noise immunity, it is still possible to transmit over 100Mbps signal over power lines, but requires better standards.

#### Optic fiber

Optic fiber is capable transmitting at extremly high speed, tens Tbps, however, it is limited by converting a electrical signal into optic signal.

Optic fiber transmission requires: light source, transmission medium, detector.

> optics with light bouncing inside is multi-mode, without that bouncing is single-mode.

Optics need either connectors, mechanically spliced, or melted together.

> optic fiber has higher bandwidth, lower attenuate, better noise immunity, lower weight, lower installation cost, better security; but it also requires better engineering, more protection, and extra bi-directional design.

### Unguided media

The modern wireless digital communication began in the Hawaiian Island - -

The basic of unguider media is electromegnatic wave, caused by the movement of a electron. It has a oscillation freq and wavelength where their product shall be light speed in vacuum.

![Electromegnatic Wave Spectrum](http://www.shieldingsystems.com/images/electromagnetic_spectrum%20.png)

Wireless communication normally transmitting in a narrow band of frequency, however, it can also use wide bandwidth:

1. Frequency hopping spread spectrum: transmitter jump from freq to freq, usually by military for harder detection.

2. Direct sequence spread spectrum: use a code sequence to spread the data to a wide bandwidth, for example, CDMA (Code Division Multiple Access).

3. Ultra Wide-Band: sends a series of rapid pulses, varying their position to communicate information.

#### Radio Transmission

Omnidirectional, transmitter and receiver do not need to align perfectly. And comparing to guided media, RF can travel longer distance, but interference between users is a problem.

#### Microwave Transmission

Microwave travel in straight line, so repeater is needed to avoid earth. And signal may be delayed due to passing lower atmosphere, called **multipath fading**

> It has advantages over fibers, because it does not take up a lot of place to embed the cable, only towers are required, and it is relatively inexpensive.

#### Infrared Transmission

For short range communication.

#### Light Transmission

LANs from two buildings could be connected via the laser on the top of both building.

> High bandwidth, low cost, and secure, although it is eaisly distorted, it could be used in vacuum in space programs.

#### Geo-stationary Satellite

There could be maximum 180 Geo-stationary satellite. Through development, footprint of satellite is shrank, from 1/3 sphere, to spot beam. And require station to transmit signal to local, from large one to small ones called VSATs.

VSATs requires ground hub to transmit signal using high power antenna.

> very useful when connecting rural area using VSATs, signal transmit faster because the medium is air, but not very secret, however, cost does not grow as distance, and error rate is low.

#### Medium-Earth Orbit Satellites

GPS.

#### Low-Earth Orbit Satellites

Gound stations don't need much power, delay is small, only ms around the earth, and price is relatively low.

#### Overall

Mostly, fibers are winning, but satellites have pros:

1. deploy could be very fast.

2. connection at rural area is achieved.

3. more suitable for broadcasting.

## Data-Link Layer

This layer has three objective:

1. [Providing services to the network layer.](#framing)

2. [Dealing with transmission error.](#error-control)

3. [Flow control](#protocols)

Three acknowledgment scheme:

1. unacknowledged connection-less: Ethernet, because the connection has very low error rate, no need to send ack.

2. acknowledged connection-less: WiFi, because the connection is unreliable, sending ack will reduce the cost to recover message.

3. connection oriented: each frame is received exactly once and all frames are received in the right sequence.

### Framing

Data-link layer is in charge of detecting, or more, correcting the error in the transmitted signal. Normal way is to break the bit sequence and framing them.

A good deisgn is when receiver is easy to find the start of a new frame and the information took up as less bandwidth as possible.

4 possible methods:

1. [Byte count](#byte-count)

2. [Flag byte with byte stuffing](#flag-byte-stuffing)

3. [Flag byte with bit stuffing](#flag-bit-stuffing)

4. [Physical layer coding violations](#physical-layer-coding-violations)

#### Byte count

Use a field to count how many byte sending in the packet.

> it is very possible that the bit flipped and the counter gives the wrong bytes, hence leading error.

#### FLAG Byte stuffing

FLAG means adding the same byte called **FLAG** to both the beginning and the end of the frame to announce the beginning and ending of a frame.

> it is possible that data contains the bit forms the **FLAG** and **ESC** Whenever sees a **ESC** or **FLAG** add a **ESC** before. PPP is one example

#### FLAG bit stuffing

FLAG has the same mining, but bit stuffing inserts bit after 5 \"1\" because \"01111110\" means **FLAG**

both of bit stuffing and byte stuffing would increase the frame size.

#### Physical layer coding violation

In physical layer, usually bits are mapped with more signals to safe guard redundency, we could utilizing extra bits to send reserved signals indicates the start and end of a frame, without needs for stuffing.

The popular method is to include a long string called **preamble**, which starts the frame, and then use a field to indicates how long a frame is.

### Error control

1. Ack is normally the way of solving the problem of letting the sender know whether the packet has arrived successfully or not.

2. Timer is used to get rid of the frame lossing trouble, so sender will not wait forever for a ACK of a lossing frame or lossing ACK frame.

3. Assign sequence number to each frame, so that receiver can know whether one frame is received twice.

There are two mean method, adding **error correcting code** and **error detecting code**.

> **error correcting code** or **FEC** is used in noisy channels because resend could likely be errors again.

bit flip is harder than erasure channel.

---

1. [Hamming codes](#hamming-codes)

2. [Binary convolutional codes](#binary-convolutional-codes)

3. [Reed-Solomon codes](#reed-solomon-codes)

4. [Low-Density Parity Check codes](#low-density-parity-check-codes)

**m** reps message length, **r** reps redundant bits, and the encoded code word length is **n = m + r**, code rate is **m/n**.

#### Hamming Codes

> Hamming distance is the number of bits positions in which two code words differes.

Firstly, all possible code words should be computed and form a list from which the minimum **Hamming Distance** should be found thus called the **Hamming Distance of whole list**. And it could be called a **Distance x code**

All possible code words should be **2^m/2^n**

With the error of **d**, we are expecting to correct it with a **Distance 2d+1 code** and detect it with a **Distance d+1 code**.

Given **m** bits message, if we wish to correct all single error, we are expecting **n+1** pattern for each of **2^m** pattern, it should be less than **2^n**, henc we have **(N+1) * 2^m <= 2^n**

Message bit **m** is checksumed by the ordering bits, for example, **m3 = p1 + p2**, **m7 = p1 + p2 + p4**

When receiving a message code, it will computes the hamming codes based on the parity, each parity bit is calculated by check the message bit it related to, if comes out odd 1s, then parity bit shall be 1; then, after receiver receives hamming code, it will recompute it, by check the parity including check bits, if all checks give 0, then it is correct, other wise it will pinpoint the error bit.

#### Binary Convolutional Codes

No natural message size and encoding boundary as in block codes, output depends on current and previous bits, number of previous bits that output depends on is the constraint length.

A Convolutional codes is specified by its rate and constraint length.

> Widely used in deployed networks, GSM, Satellite, Wi-Fi, NASA [r=1/2, k=7] code is used in Voyager program and reused in Wi-Fi.

For Wi-Fi, there should be 6 memory registers, when 111 input in, 000000 -> 100000 -> 110000 -> 111000, and 7 bits input is required to wipe out all previous input, hence k=7.

> To decode the convolutional code is to find the input sequence that is most likely to generate the output bits. Viterbi Algorithm is used in this codes.

Using Viterbi algorithm error correcting and working with uncertain bits is **soft-decision decoding**, deciding which bits the signal is before error correcting is called **hard-decision decoding**.

#### Reed-Solomon Codes

Reed-solomon codes is a linear block code, but it works on byte.

> it works based on the fact tha tany n-degree polynomial uniquely determined by the n+1 points' positions.

This method means, any two signal points sits on a line, we could add two more points on this line as redudant, one signal is error, three are on the line, and the one is not on the line is the error symbol, and we could hence correct the error.

Most popular RS code is (255,223) code, where it could error correct based on byte, 255 = 2^8 - 1, where 223 = 2^8 - 1 - 2 * 16, where 16 is the symbol-error corerecting ability of this code.

> it could be used with convolutional code, and correct both burst and single error.

#### Low-Density Parity Check Codes

In this codes, each output is computed with a fraction of input, where matrix rep of a code has low density of 1s.

While decoding, it will use an approximation algorithm to iteratively improves the best fit of the incoming data to a legal codeword.

> Very high error correcting ability, outperform above codes, and widely used in new protocols.

---

1. [Parity](#parity)

2. [Checksums](#checksums)

3. [Cyclic Redundancy Checks](#cyclic-redundancy-checks)

#### Parity

Simple idea is that even 1 then add 0, odd 1 then add 1, it can detect single error.

Compare to Hamming Code, for 1,000 bits info block, Hamming Codes requires 10 bits for correction, 1,000,000 bits requires 10,000 bits check. Where with error rate at 10^-6, for every one of the 1000 blocks, 1 will be error, to detect and retransmit it, one extra block of 1001 is required, hence total will cost 2002 bits, is significantly smaller than hamming 10,000 bits.

> We could use interleaving to deal with burst errors.

#### Checksums

Calculating a number based on the information and appended to the information, any error will cause the mis-recomputation of the checksum hence leads to error.

#### Cyclic Redundancy Checks

CRC is also known as polynomial code, it requires both sender and receiver agree on a generator, then if the receiver receives a code that cannot be fully divide by the generator, it means there is an error.

### Protocols

Data-Link Layer protocols defines how to encapsulate **packet** from network layer to **frame**, and it handles certain amount flow control and error control.

1. [Utopia Simplex Protocol](#utopia-simplex-protocol)

2. [Simplex Stop-and-Wait Protocol for Error-Free Connection](#simplex-stop-and-wait-protocol-for-error-free-connection)

3. [Simplex Stop-and-Wait Protocol for Noisy Connection](#simplex-stop-and-wait-protocol-for-noisy-noisy-connection)

4. [One-bit Sliding Window Protocol](#one-bit-sliding-window-protocol)

5. [Go-Back-N Protocol](#go-back-n-protocol)

6. [Selective Repeat Protocol](#selective-repeat-protocol)

#### Utopia Simplex Protocol

This protocol concerns nothing but the actual transfer, is unrealisti scenario.

#### Simplex Stop-and-Wait Protocol for Error-Free Connection

Considering flow control to preventing the sender flooding the receiver.

Two major schemes, one is **feedback-based flow control**

> receiver send feedback to allow sender to continue send packets, or tell it how receiver is going on processing packets.

this requires at least a half-duplex channel to be implemented on.

the other one is **rate-based flow control**

> protocol has built-in mechanism to limit the sender's sending rate.

#### Simplex Stop-and-Wait Protocol for Noisy Connection

It could be adding timer to the sender, when the ack is not sent to the sender, and the timer is out, the sender will resend the frame. Problem is, scenarios exist that ack is lost so that the frame will be duplicated.

1 bit of seq number is enough for ack this frame and the next frame.

For this protocol, both sender and receiver should remember the next frame's seq, damaged ack is sent the same as the last good ack, and data is sent from the buffer.

#### One-bit Sliding Window Protocol

Sliding window protocol with the size of 1, which means all frames received must be in order.

In a duplex connection, if both sides decide to send frame simultaneously, error will occur.

#### Go-Back-N Protocol

One-bit will decrease the bandwidth utilization, hence increase the bits so that the sender could (ideally) continuously sending the frames.

Hence we would consider how many frames can fit into the channel as the frames are propagated from sender to the receiver.

This could be calculated by **product the Bandwidth(bits/sec) with the one time propagation delay**, with this value named **BD**, and the max frames to fit inside this channel is **2BD + 1**.

This is the max frames to be coexisted on the channel, due to it ingores the processing time and the ack frame length.

Cumulative Ack means that the incoming of ACK N also ack the N-1, N-2.

#### Selective Repeat Protocol

Selective repeat improves the go back N by letting the sender only retransmit the error frame, it will normally send a negative ack to force the sender to retransmit without waiting for the expiry of the timer. And if the NACK is lost, the sender will only send the losing frame again.

## Media Access Control Sublayer

MAC sublayer is important in broadcasting network, important in LAN especially for wireless network.

### Static Channel Allocation

Frequency Division Multiplexing: for N users, channel is divided into N frequency bands, hence each user has its own band, without interfering

### Dynamic Channel Allocation

#### ALOHA and Slotted ALOHA

ALOHA allows different stations sends the frames whenever they need to, a collision would leads to retransmission, it has the best output at expected frame = 0.5 with successful rate at 0.18.

Slotted ALOHA requires stations send frames at the beginning of a slot, it has the best performance at expected frame = 1 with successful rate at almost 0.37.

#### Carrier Sense Multiple Access Protocol

- 1-persistent CSMA: when a station finds out the channel is busy, it will wait, when it sees it is idle, it will 100% sure start transmission.
> Propagation delay would influence on it, 100% certainty of transmission is bad, if propagation delay is small, then collision possiblity is small.

- nonpersistent CSMA: same as 1-persistent CSMA, only it will wait a random period of time till it start transmitting, but it adds delay.

- p-persistent CSMA: used on slotted channel, when channel is idle, it has __p__ percent chance of transmitting, otherwise wait till the next slot.

- CSMA with Collision Detection: when the collision happens, the stations detect it and stop transmission immediately, and it will wait 2 times propagation delay for the sender to ack the collision, hence the frame length would better be 2t.

- CSMA with Collision Detection: when the collision happens, the stations detect it and stop transmission immediately, and it will wait 2 times propagation delay for the sender to ack the collision, hence the frame length would better be 2t.

#### Collision-Free Protocol

- Bit-map protocol: for channel of N contention, it will has N slots, for j station which has frame to send, it will transmit a 1 on j slot, and then by the slots, frames are transmitted. When the channel load are growing higher, the performance ioncreases.

- Token Passing: only with the token, a station is allowed to send a frame. Also known as token bus.
> There has been FDDI(Fiber Distributed Data Interface) and RPR(Resilient Packet Ring)

- Binary Countdown: Since Bit-map and token passing both need 1 bit overhead, binary addressing could save a lot while there exist a lot stations. In this protocol, every bit time, if a station has frame to send, it will send its address, if sent 0 saw 1, the station will quit contention. The one with the final binary seq address will send the frame. A high numbered station has high priority.

#### Limited Contention Protocol

Use contention protocol at low load to save delay and collision-free at high load to increase efficiency.

- Adaptive Tree Walk protocol: using depth-first tree to permit the transmission.

#### Wireless LAN Protocol

> Exposed and Hidden Terminal: A Hidden terminal is that a transmitting station that is beyond the range of the current station; a Exposed terminal is that a two transmitting station has no collision on receiver but can see each other transmitting.

- MACA(Multiple Access with Collision Avoidance): Sender sends RTS(Request To Send) to stimulate the receiver to send a CTS(Clear To Send) to pause receiver nearby stations to stop transmitting, then the actual data frame is sent.

### Ethernet

Classic and switched ethernet: Classic Ethernet solves multiple access as above, switched network uses a switch device.

## Network Layer

Network Layer concerns how to get the packet to the destination, is the lowest layer of end to end transmission.

- [Network Layer Design Issues](#network-layer-design-issues)

- [Routing Algorithms](#routing-algorithms)

- [Congestion Control Algorithms](#congestion-control-algorithms)

- [Quality of Service](#quality-of-service)

- [Internetworking](#internetworking)

---

### Network Layer Design Issues

#### Store-and-Forward Packet Switching

The major components are the ISP(Internet Service Provider) devices and customer devices. These devices are used as the packet is stored until it has fully arrived and checksum finished, then it will be forward to the next router.

#### Service Provided

1. The services should be independent of the router technology.

2. The transport layer shold be shielded from the number, type, and topology of the router.

3. The network address made available to the transport layer should use a uniform numbering plan, even across LAN and WAN.

These leads to the argue that whether the network layer should provide connection-oriented or connectionless services.

For one side, routers' job is moving the packets around, hence connectionless, and for the other side, it is said that a connection ensures quality of services.

#### Connectionless

The ISP router decides which is the next stop by a routing table, the routing table gives the next stop by the final destination, and the routing table is managed by the routing algorithm.

#### Connection-oriented

Label switching is the machanism used in this service, when a ISP router sees a packet from Host 1 with label 1, it will label it with identifier 1 and route it to the next router, any other connection from other host or head different destination will be assign different identifier.

#### Datagram vs Virtual-Circuit

Trade-offes:

1. Setup time vs Address parsing time

2. Destination address used in datagram are longer than circuit numbers used in VC because they have a global meaning.

3. Amount required in router memory.

4. Scenario based connection.

5. Router crashes leads to the loss of connection has significant effect on the connection-oriented service comparing to connectionless service.

---

### Routing Algorithms

Datagram needs routing for every packet, but the VC needs one for setup session, hence it is also named as session routing.

Two kinds of routing algorithms: Adaptive and non-adaptive.

#### The Optimality Principle

If J is on the optimal route from I to K, then the optimal path from J to K is also on this path.

#### Shortest Path Algorithm

Examine adjcent nodes of current working nodes, assign distance, then, after examine all the adjcent nodes, if the path is the shortest to this node, then made the label permenant, and using the one node with the smallest label as the new working node.

#### Flooding

Every packet is sent out on every path except for the one it arrived on.

> Hop counter: it is used to countdown for a fixed length of the packet can be hopped around, it the counter counts down to 0, the packet is discarded. This avoids the infinite hop of a packet in the network.
---
> Another method is to avoid flooding a packet has been flooded by using a packet seq with source machine.

It is good to be used on the broadcast network and very robust.

#### Distance Vector Routing

For current working router, its neighbors will report their delay to destination as X, and the router itself holds the delay to the neighbors as m, by calc X+m, a minimum value will be the shortest route.

> Convergence: Good news propagates quickly, bad news take a very long time.

#### Link State Routing

1. Learning about the neighbours:

2. Setting Link Costs:

3. Building Link State Packets:

4. Distributing the LSP:

5. Computing the New Routes:

#### Hierachical Routing

#### Broadcast Routing

#### Multicast Routing

#### Anycast Routing

#### Routing for Mobile Hosts

#### Routing in Ad Hoc  Networks

---

### Internetworking

| Item | Some Possibilities |
| --- | :---: |
| Service Offered | Connectionless vs Connection Oriented|
| Addressing | Different Size, Flat and Hierarchical |
| Broadcasting | Present or Absent |
| Packet Size | Depends on network |
| Ordering | Ordered or Unordered Delivery |
| QoS | Many different kinds |
| Reliability | Different Level |
| Security | Privacy Rules |
| Parameters | Different Timeout |
| Accounting | By connect time, packet |

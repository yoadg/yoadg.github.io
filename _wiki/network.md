---
layout: page
title: Computer Networks
permalink: /wiki/network/
date: 2023-04-23
categories: 
  - network
tags:
  - internet
  - tcp/ip
  - osi
  - dns
---
A *computer network* is a set of interconnected computing devices that can exchange data and share resources with each other. Computers are connected over digital interconnections that are made up of telecommunication network technologies, based on physically wired, optical, and wireless radio-frequency (RF) methods, and may be arranged in a variety of network topologies. The network permits nodes connected to it to transfer messages to other nodes by merely providing the content of a message and the address of the destination node and letting the network find the way to deliver the message to the destination node. Each connected device is uniquely identified within a network segment by the Media Access Control (MAC) address, which is assigned to a Network Interface Controller (NIC).

Computers use common [communication protocols](/wiki/protocols) that define rules for exchanging information over the network. Communication protocols have various characteristics. They may be connection-oriented or connectionless, they may use circuit mode or packet switching, and they may use hierarchical addressing or flat addressing. In a protocol stack, communications functions are divided up into protocol layers, where each layer leverages the services of the layer below it until the lowest layer controls the hardware that sends information across the media. 

## OSI Model 
The Open Systems Interconnection (OSI) model is a conceptual model that provides a common basis for the coordination of standards development for the purpose of systems interconnection. It also defines a logical network and effectively describes computer packet transfer. The OSI Model can be seen as a universal language for computer networking. It is essentially a reference system that lays out how computers communicate with each other over a network. It's based on the concept of splitting up a communication system into seven abstract layers, each one stacked upon the last.

The seven layers are:
1. **Physical layer** – This layer is responsible for the transmission and reception of unstructured raw data between a device, and a physical transmission medium. It receives *frames* in the form of digital bits and converts them into analog or digital signals, propagating them through channels such as coaxial cable, fiber optic cable, DSL cable, etc. 
2. **Data Link layer** – This layer provides direct node-to-node data transfer. It detects and possibly corrects errors that may occur in the physical layer. It defines the protocol to establish and terminate a connection between two physically connected devices.
3. **Network layer** – This layer provides the functional and procedural means of transferring small units of data, called *packets*, between two different networks. Each packet is enriched with a source and destination IP address, which uniquely identifies a node in the network. The Network layer also finds the best physical path for the data to reach its destination (known as routing). Message delivery at this layer is not necessarily guaranteed to be reliable.
4. **Transport layer** – This layer provides the functional and procedural means of transferring variable-length data  between two devices across a network, while maintaining the Quality-of-Service (QoS) functions. This may require breaking large protocol data units or long data streams into smaller chunks called *segments*. Each segment is enriched with a source and destination port. Transport protocols may be connection-oriented or connectionless.
5. **Session layer** – This layer creates the setup, controls the connections, and ends the teardown, between two or more computers, which is called a *session*. It ensures that the session stays open long enough to transfer all the data being exchanged, and then promptly closes the session in order to avoid wasting resources. 
6. **Presentation layer** – This layer establishes data formatting and data translation into a format specified by the application layer during the encapsulation of outgoing messages while being passed down the protocol stack (serialization), and possibly reversed during the decapsulation of incoming messages when being passed up the protocol stack (deserialization). Other functions of the Presentation layer are encryption and compression. 
7. **Application layer** – This layer, which is implemented in software, is the only layer that directly interacts with data from the user. Applications like web browsers and email clients rely on the application layer to initiate communication through protocols such as HTTP and SMTP. 

![Computer network](/assets/images/network.png)

*Computer network models*

## Internet Protocol Suite
The Internet protocol suite, commonly known as *TCP/IP*, is a framework for organizing the set of communication protocols used in the Internet and similar computer networks according to functional criteria. This suite provides end-to-end data communication specifying how data should be packetized, addressed, transmitted, routed, and received.

The TCP/IP model is a concise version of the OSI model. It contains four layers, unlike seven layers in the OSI model. The layers are:
1. **Link / Network Access layer** - corresponds to the combination of Data Link layer and Physical layer of the OSI model. This is layer is implemented in a hardware part like a NIC, which enables the physical transmission of data.
2. **Internet layer** – parallels the functions of OSI’s Network layer. It defines the protocols which are responsible for logical transmission of data over the entire network. The main protocol residing at this layer is in the Internet Protocol (IP).
3. **Transport / Host-to-Host layer** – analogous to the transport layer of the OSI model. It is responsible for end-to-end communication and error-free delivery of data. It shields the upper-layer applications from the complexities of data. The two main protocols present in this layer are: [Transmission Control Protocol (TCP)](#tcp) and [User Datagram Protocol (UDP)](#udp).
4. **Application / Process layer** – performs the functions of the top three layers of the [OSI model](#osi-model): Application, Presentation and Session layer. It is responsible for node-to-node communication and controls user-interface specifications. Some of the protocols present in this layer are: HTTP, HTTPS, FTP, TFTP, Telnet, SSH, SMTP, SNMP, NTP, DNS, DHCP, NFS, X Window and LPD. 

### Internet Protocol 
The Internet Protocol (IP) is the network layer communications protocol in the Internet protocol suite for relaying datagrams across network boundaries. Its routing function enables internetworking, and essentially establishes the Internet. IP defines packet structures that encapsulate the data to be delivered. It also defines addressing methods that are used to label the datagram with source and destination information. IP information is attached to each packet, and this information helps routers to send packets to their destination, based on the IP addresses in the packet headers. Every device or domain that connects to the Internet is assigned an IP address and each IP packet contains both the IP address of the device or domain sending the packet and the IP address of the intended recipient.

An IP address is a unique identifier assigned to a device or domain that connects to the Internet. Each IP address is a unique sequence of numbers, such as 192.168.1.1 (IPv4) or 2345:0425:2CA1:0000:0000:0567:5673:23b5 (IPv6). It globally identifies every device in the interconnected network. Users are able to access websites without memorizing this complex series of characters via [Domain Name System (DNS)](#dns) resolvers, which translate human-readable domain names into IP addresses. 

### IPV4 vs. IPV6
IP version 4 (IPv4) that was launched in 1983 is still the most widely used version of the Internet Protocol. It's a 32-bit address which is made up of 4 blocks – with each block being in the range of 0-255 and separated by a dot. IPv4 can provide up to 232 unique addresses (approx. 4.3 billion addresses) for different devices. 

IP version 6 (IPv6) is the latest version of the Internet Protocol which was first deployed in 1998. Also known as IPng (Internet Protocol next generation), it is more advanced, secure, and faster than IPv4. IPv6 uses 8 blocks that contain 4 hexadecimal characters each, separated by a colon. It's a 128-bit address, meaning that there are 2128 (340 undecillion) addresses available. IPv6 is replacing IPv4 to accommodate the growing number of networks worldwide and help solve the IP address exhaustion problem.

### DNS
The Domain Name System (DNS) is the hierarchical and distributed naming system used to identify computers reachable through the Internet or other IP networks. The resource records contained in the DNS associate domain names with other forms of information. These are most commonly used to map human-friendly domain names to the numerical IP addresses computers need to locate services and devices using the underlying network protocols, but have been extended over time to perform many other functions. 

DNS lookup involves the following eight steps:
1. A user types a URL or clicks on a link that contains a host name, such as github.com into a web browser. 
2. The OS sends the query to a DNS resolver, which recursively queries a DNS root name server.
3. The root server responds to the resolver with the address of a Top Level Domain (TLD).
4. The resolver then makes a request to the .com TLD.
5. The TLD server then responds with the IP address of the domain's name server. 
6. Lastly, the recursive resolver sends a query to the domain's name server.
7. The IP address for github.com is then returned to the resolver from the name server (140.82.121.4). 
8. The DNS resolver then responds to the web browser with the IP address of the domain requested initially.

### UDP
The User Datagram Protocol (UDP) is one of the core communication protocols of the Internet protocol suite used to send messages (transported as datagrams in packets) to other hosts on an IP network. Within an IP network, UDP is a fast, simple and efficient protocol that does not require prior communication to set up communication channels or data paths. UDP provides checksums for data integrity, and port numbers for addressing different functions at the source and destination of the datagram. UDP has no handshaking dialogues and therefore it doesn't guarantee that all data is successfully transferred. With UDP, data is sent to any device that happens to be listening, but it doesn't care if some of it is lost along the way. This is one of the reasons why UDP is also known as the "fire-and-forget" protocol. UDP is used for situations where some data loss is acceptable, like live video/audio, or where speed is a critical factor like online gaming.

### TCP
The Transmission Control Protocol (TCP) is the most common transport protocol of the Internet protocol suite. It originated in the initial network implementation in which it complemented the Internet Protocol. Therefore, the entire suite is commonly referred to as TCP/IP. TCP provides reliable, ordered, and error-checked delivery of a stream of octets (bytes) between applications running on hosts communicating via an IP network. TCP is connection-oriented, and a connection between client and server is established before data can be sent. The server must be listening (passive open) for connection requests from clients before a connection is established. Once a connection has been established, data can be transmitted in both directions. TCP has built-in mechanisms to check for errors and to guarantee data will be delivered in the order it was sent, making it extremely reliable. TCP is used in situations where it's necessary that all data being sent by one device is received by another completely intact, such as web browsing (HTTP), email sending (SMTP), and file transfering (FTP).

## Network Types
### Geographic Scale
Networks can be characterized by physical extent or geographic scale, such as:
- **Personal Area Network (PAN)** – a computer network used for communication among computers and different information technological devices close to one person. The reach of a PAN typically extends to 10 meters. A wired PAN is usually constructed with USB and FireWire connections while technologies such as Bluetooth (BT) and infrared (IR) communication typically form a wireless PAN.
- **Local Area Network (LAN)** – a network that connects computers and devices in a limited geographical area such as a home, school, office building, or closely positioned group of buildings. Wired LANs are most commonly based on Ethernet technology. Wireless LANs are based on the IEEE 802.11 standard, known as WiFi. A LAN can be connected to a wide area network (WAN) using a router. 
- **Backbone Network** – part of a computer network infrastructure that provides a path for the exchange of information between different LANs or subnetworks. A backbone can tie together diverse networks within the same building, across different buildings, or over a wide area. The Internet backbone is a massive, global system of fiber-optic cable and optical networking that carry the bulk of data between WANs, metro, regional, national and transoceanic networks.
- **Wide Area Network (WAN)** – a computer network that covers a large geographic area such as a city, country, or spans even intercontinental distances. A WAN uses a communications channel that combines many types of media such as telephone lines, cables, and airwaves. WAN technologies generally function at the lower three layers of the [OSI model](#osi-model): the physical layer, the data link layer, and the network layer.

### Organizational Scope
Networks are typically managed by the organizations that own them. We usually distinguish between:
- **Intranet** – a set of networks that are under the control of a single administrative entity. The intranet uses the IP protocol and IP-based tools such as web browsers and file transfer applications. The administrative entity limits the use of the intranet to its authorized users. Most commonly, an intranet is the internal LAN of an organization. 
- **Internet** – a global system of interconnected governmental, academic, corporate, public, and private computer networks. It is based on the networking technologies of the Internet Protocol Suite. The Internet utilizes copper communications and the optical networking backbone to enable the World Wide Web (WWW), the Internet of Things (IoT), video transfer, and a broad range of information services.
- **Virtual Private Network (VPN)** – an overlay network in which some of the links between nodes are carried by open connections or virtual circuits in some larger network (e.g., the Internet) instead of by physical wires. The data link layer protocols of the virtual network are said to be tunneled through the larger network when this is the case. VPN enables host-to-network communication, which is analogous to connecting a computer to a LAN. This type of VPN provides access to an enterprise network, such as an intranet. 







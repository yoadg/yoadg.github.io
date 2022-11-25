---
layout: page
title: Computer Networking
permalink: /wiki/network/
categories: 
  - network
---
A c*omputer network* is a set of interconnected computing devices that can exchange data and share resources with each other. Computers are connected over digital interconnections that are made up of telecommunication network technologies, based on physically wired, optical, and wireless radio-frequency (RF) methods, and may be arranged in a variety of network topologies. The network permits nodes connected to it to transfer messages to other nodes by merely providing the content of a message and the address of the destination node and letting the network find the way to deliver the message to the destination node. 

Computers use common communication protocols that define rules for exchanging information over the network. Communication protocols have various characteristics. They may be connection-oriented or connectionless, they may use circuit mode or packet switching, and they may use hierarchical addressing or flat addressing. In a protocol stack, communications functions are divided up into protocol layers, where each layer leverages the services of the layer below it until the lowest layer controls the hardware that sends information across the media. 

## Open Systems Interconnection Model 
The Open Systems Interconnection (OSI) model is a conceptual model that provides a common basis for the coordination of standards development for the purpose of systems interconnection. It also defines a logical network and effectively describes computer packet transfer. The OSI Model can be seen as a universal language for computer networking. It is essentially a reference system that lays out how computers communicate with each other over a network. It's based on the concept of splitting up a communication system into seven abstract layers, each one stacked upon the last.

The seven layers are:
1. **Physical layer** – this layer is responsible for the transmission and reception of unstructured raw data between a device, and a physical transmission medium. It converts the digital bits into electrical, radio, or optical signals. 
2. **Data Link layer** – this layer provides direct node-to-node data transfer. It detects and possibly corrects errors that may occur in the physical layer. It defines the protocol to establish and terminate a connection between two physically connected devices.
3. **Network layer** – this layer provides the functional and procedural means of transferring small units of data, called packets, between two different networks. Many nodes may be connected to a single network, where each of them has a unique address. The network layer also finds the best physical path for the data to reach its destination (known as routing). Message delivery at the network layer is not necessarily guaranteed to be reliable.
4. **Transport layer** – this layer provides the functional and procedural means of transferring variable-length data between two devices across a network, while maintaining the quality-of-service (QoS) functions. This may require breaking large protocol data units or long data streams into smaller chunks called "segments". Transport protocols may be connection-oriented or connectionless.
5. **Session layer** – this layer creates the setup, controls the connections, and ends the teardown, between two or more computers, which is called a "session". The session layer ensures that the session stays open long enough to transfer all the data being exchanged, and then promptly closes the session in order to avoid wasting resources. 
6. **Presentation layer** – this layer establishes data formatting and data translation into a format specified by the application layer during the encapsulation of outgoing messages while being passed down the protocol stack, and possibly reversed during the deencapsulation of incoming messages when being passed up the protocol stack. The functions of the presentation layer are translation (serialization/deserialization), encryption/decryption, and compression.
7. **Application layer** – this layer, which is implemented in software, is the only layer that directly interacts with data from the user. Applications like web browsers and email clients rely on the application layer to initiate communication through protocols such as HTTP and SMTP. 

![Computer network](/assets/images/network.png)

*Computer network models*

## Internet Protocol Suite
The Internet protocol suite, commonly known as *TCP/IP*, is a framework for organizing the set of communication protocols used in the Internet and similar computer networks according to functional criteria. This suite provides end-to-end data communication specifying how data should be packetized, addressed, transmitted, routed, and received.

The TCP/IP model is a concise version of the OSI model. It contains four layers, unlike seven layers in the OSI model. The layers are:
1. **Link / Network Access layer** - corresponds to the combination of Data Link layer and Physical layer of the OSI model. It looks out for hardware addressing and the protocols present in this layer allows for the physical transmission of data.
2. **Internet layer** – parallels the functions of OSI’s Network layer. It defines the protocols which are responsible for logical transmission of data over the entire network. The main protocol residing at this layer is in the Internet Protocol (IP).
3. **Transport / Host-to-Host layer** – analogous to the transport layer of the OSI model. It is responsible for end-to-end communication and error-free delivery of data. It shields the upper-layer applications from the complexities of data. The two main protocols present in this layer are: Transmission Control Protocol (TCP) and User Datagram Protocol (UDP)
4. **Application / Process layer** – performs the functions of the top three layers of the OSI model: Application, Presentation and Session layer. It is responsible for node-to-node communication and controls user-interface specifications. Some of the protocols present in this layer are: HTTP, HTTPS, FTP, TFTP, Telnet, SSH, SMTP, SNMP, NTP, DNS, DHCP, NFS, X Window and LPD. 

### Internet Protocol 
The Internet Protocol (IP) is the network layer communications protocol in the Internet protocol suite for relaying datagrams across network boundaries. Its routing function enables internetworking, and essentially establishes the Internet. IP defines packet structures that encapsulate the data to be delivered. It also defines addressing methods that are used to label the datagram with source and destination information. IP information is attached to each packet, and this information helps routers to send packets to their destination, based on the IP addresses in the packet headers. Every device or domain that connects to the Internet is assigned an IP address and each IP packet contains both the IP address of the device or domain sending the packet and the IP address of the intended recipient.

An IP address is a unique identifier assigned to a device or domain that connects to the Internet. Each IP address is a unique sequence of numbers, such as 192.168.1.1 (IPv4) or 2345:0425:2CA1:0000:0000:0567:5673:23b5 (IPv6). It globally identifies every device in the interconnected network. Users are able to access websites without memorizing this complex series of characters via Domain Name System (DNS) resolvers, which translate human-readable domain names into IP addresses. 

### IPV4 vs. IPV6
IP version 4 (IPv4) that was launched in 1983 is still the most widely used version of the Internet Protocol. It's a 32-bit address which is made up of 4 blocks – with each block being in the range of 0-255 and separated by a dot. IPv4 can provide up to 232 unique addresses (approx. 4.3 billion addresses) for different devices. 

IP version 6 (IPv6) is the latest version of the Internet Protocol which was first deployed in 1998. Also known as IPng (Internet Protocol next generation), it is more advanced, secure, and faster than IPv4. IPv6 uses 8 blocks that contain 4 hexadecimal characters each, separated by a colon. It's a 128-bit address, meaning that there are 2128 (340 undecillion) addresses available. IPv6 is replacing IPv4 to accommodate the growing number of networks worldwide and help solve the IP address exhaustion problem.

### Domain Name System
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

### User Datagram Protocol
The User Datagram Protocol (UDP) is one of the core communication protocols of the Internet protocol suite used to send messages (transported as datagrams in packets) to other hosts on an IP network. Within an IP network, UDP is a fast, simple and efficient protocol that does not require prior communication to set up communication channels or data paths. UDP provides checksums for data integrity, and port numbers for addressing different functions at the source and destination of the datagram. UDP has no handshaking dialogues and therefore it doesn't guarantee that all data is successfully transferred. With UDP, data is sent to any device that happens to be listening, but it doesn't care if some of it is lost along the way. This is one of the reasons why UDP is also known as the "fire-and-forget" protocol. UDP is used for situations where some data loss is acceptable, like live video/audio, or where speed is a critical factor like online gaming.

### Transmission Control Protocol
The Transmission Control Protocol (TCP) is the most common transport protocol of the Internet protocol suite. It originated in the initial network implementation in which it complemented the Internet Protocol. Therefore, the entire suite is commonly referred to as TCP/IP. TCP provides reliable, ordered, and error-checked delivery of a stream of octets (bytes) between applications running on hosts communicating via an IP network. TCP is connection-oriented, and a connection between client and server is established before data can be sent. The server must be listening (passive open) for connection requests from clients before a connection is established. Once a connection has been established, data can be transmitted in both directions. TCP has built-in mechanisms to check for errors and to guarantee data will be delivered in the order it was sent, making it extremely reliable. TCP is used in situations where it's necessary that all data being sent by one device is received by another completely intact, such as web browsing (HTTP), email sending (SMTP), and file transfering (FTP).








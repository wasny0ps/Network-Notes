# OSI Model

OSI stands for Open Systems Interconnection. It has been developed by ISO – ‘International Organization for Standardization‘, in the year 1984. It is a **7 layer architecture with each layer having specific functionality to perform**. All these 7 layers work collaboratively to transmit the data from one person to another across the globe.

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x2%20-%20OSI%20Model%20%26%20Commonly%20Used%20Protocols/source/OSI_Model.png"></p>



## Physical Layer (Layer 1)

**The lowest layer of the OSI reference model** is the physical layer. It is responsible for the actual physical connection between the devices. The physical layer contains information in the form of **bits**. It is responsible for transmitting individual bits from one node to the next. **When receiving data, this layer will get the signal received and convert it into 0s and 1s and send them to the Data Link layer, which will put the frame back together**. 

> Hub, Repeater, Modem, Cables are Physical Layer devices.


## Data Link Layer (Layer 2)

The data link layer is **responsible for the node-to-node delivery of the message**. The main function of this layer is to make sure data transfer is error-free from one node to another, over the physical layer. When a packet arrives in a network, it is the responsibility of DLL to transmit it to the Host using its **MAC address**. Data Link Layer is divided into two sublayers: 

- **Logical Link Control (LLC)**
* **Media Access Control (MAC)**

The packet received from the Network layer is further divided into frames depending on the **frame** size of **NIC(Network Interface Card)**. **DLL also encapsulates Sender and Receiver’s MAC address in the header**. 

The Receiver’s MAC address is **obtained by placing an ARP(Address Resolution Protocol)** request onto the wire asking “Who has that IP address?” and the destination host will reply with its MAC address.

> Packet in Data Link layer is referred to as **Frame**. **Switch & Bridge are Data** Link Layer devices.

## Network Layer (Layer 3)

The network layer works for the transmission of data from one host to the other located in different networks. **It also takes care of packet routing selection of the shortest path to transmit the packet, from the number of routes available**. **The sender & receiver’s IP addresses are placed in the header by the network layer**. The functions of the Network layer are :  

- **Routing**: The network layer protocols determine which route is suitable from source to destination. This function of the network layer is known as routing.
* **Logical Addressing**: In order to identify each device on internetwork uniquely, the network layer defines an addressing scheme. The sender & receiver’s IP addresses are placed in the header by the network layer. Such an address distinguishes each device uniquely and universally.

> **Segment** in Network layer is referred to as Packet. Network layer is implemented by networking devices such as **routers**.

> Some firewalls are working on Network Layer. 

## Network Layer (Layer 4)

**The transport layer provides services to the application layer and takes services from the network layer**. The data in the transport layer is referred to as **Segments**. It is responsible for the End to End Delivery of the complete message. **The transport layer also provides the acknowledgement of the successful data transmission and retransmits the data if an error is found**. Transport Layer is called as **Heart of OSI model**. The functions of the transport layer are as follows:  

- **Segmentation and Reassembly**: This layer accepts the message from the session layer, and breaks the message into smaller units. **Each of the segments produced has a header associated with it. The transport layer at the destination station reassembles the message**.

* **Service Point Addressing**: In order to deliver the message to the correct process, the transport layer header includes a type of address called service point address or port address. Thus by specifying this address,**the transport layer makes sure that the message is delivered to the correct process**.

> Data in the Transport Layer is called as **Segments**. Transport layer is operated by the Operating System. It is a part of the OS and **communicates with the Application Layer by making system calls**. 

## Session Layer (Layer 5)

This layer is responsible for the **establishment of connection, maintenance of sessions, authentication, and also ensures security**.

- **All the below 3 layers(including Session Layer) are integrated as a single layer in the TCP/IP model as “Application Layer”**.

> Implementation of these 3 layers is done by the network application itself. These are also known as Upper Layers or Software Layers. 

## Presentation Layer (Layer 6)

The presentation layer is also called the **Translation layer**. The data from the application layer is extracted here and manipulated as per the required format to transmit over the network. The functions of the presentation layer are : 

- **Translation**
- **Encryption/ Decryption**
- **Compression**


##  Application Layer (Layer 7)

At the very top of the OSI Reference Model stack of layers, we find the Application layer which is implemented by the network applications. **These applications produce the data, which has to be transferred over the network**. This layer also serves as a window for the application services to access the network and for displaying the received information to the user. 

> Some firewalls are working on Application Layer.

## TCP 

TCP (Transmission Control Protocol) is one of the main protocols of the Internet protocol suite. **It lies between the Application and Network Layers** which are used in providing reliable delivery services. It is a **connection-oriented protocol** for communications that helps in the exchange of messages between different devices over a network. The Internet Protocol (IP), which establishes the technique for sending data packets between computers, works with TCP. TCP uses a three-way handshake to establish a reliable connection.

### Three Way Handshake

The connection is full duplex, and both sides synchronize (SYN) and acknowledge (ACK) each other. The exchange of these four flags is performed in three steps are SYN, SYN-ACK, and ACK as shown in picture.

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x2%20-%20OSI%20Model%20%26%20Commonly%20Used%20Protocols/source/tcp_three_way_handshake.png"></p>

- **Step 1 (SYN)** : In the first step, the client wants to establish a connection with a server, so it sends a segment with SYN(Synchronize Sequence Number) which informs the server that the client is likely to start communication and with what sequence number it starts segments with.

- **Step 2 (SYN+ACK)** : Server responds to the client request with SYN-ACK signal bits set. Acknowledgement(ACK) signifies the response of the segment it received and SYN signifies with what sequence number it is likely to start the segments with.

- **Step 3 (ACK)** : In the final part client acknowledges the response of the server and they both establish a reliable connection with which they will start the actual data transfer.

## UDP

UDP (User Datagram Protocol) is a communications protocol, used across the Internet. It is specifically used for **time-sensitive transmissions** such as video playback or DNS lookups. It works by creating a connectionless transmission model that **requires a minimum protocol mechanism**.

UDP enables process-to-process communication and works by using Internet Protocols to encapsulate data in a UDP packet. This packed has its header information edited to include; source,destination ports, packet length and checksum. After UDP packets are encapsulated in an Internet Protocol packet, they’re sent off to their destinations.

It is best used for real time services such as:

- Gaming
- Voice or video communication
- Live conferences

> A downside to using UDP is that it is an **unreliable protocol** as it doesn’t require an established connection prior to data transfer.

## TCP vs UDP

| Basics | TCP| UDP|
|---|---|---|
|Type of Service|TCP is a connection-oriented protocol. Connection-orientation means that the communicating devices should establish a connection before transmitting data and should close the connection after transmitting the data.|UDP is the Datagram-oriented protocol. This is because there is no overhead for opening a connection, maintaining a connection, and terminating a connection. UDP is efficient for broadcast and multicast types of network transmission.|
|Reliability	|TCP is reliable as it guarantees the delivery of data to the destination router.	|The delivery of data to the destination cannot be guaranteed in UDP.|
|Error checking mechanism	| TCP provides extensive error-checking mechanisms because of it provides flow control and acknowledgment of data.|UDP has only the basic error checking mechanism using checksums.|
|Acknowledgment| An acknowledgment segment is present.| No acknowledgment segment.|
|Sequence| Sequencing of data is a feature of TCP. This means that packets arrive in order at the receiver.	|There is no sequencing of data in UDP. If the order is required, it has to be managed by the application layer.|
|Speed| TCP is comparatively slower than UDP.	|UDP is faster, simpler, and more efficient than TCP.|
|Retransmission| Retransmission of lost packets is possible in TCP, but not in UDP.	|There is no retransmission of lost packets in UDP.|
|Header Length| TCP has a 20-60 bytes variable length header.	|UDP has an 8 bytes fixed-length header.|
|Weight| TCP is heavy-weight.	| UDP is lightweight.|
|Handshaking Techniques|Uses handshakes such as SYN, ACK, SYN-ACK| It’s a connectionless protocol which means no handshake.|
|Broadcasting	|TCP doesn’t support Broadcasting.| UDP supports Broadcasting.|
|Stream Type| The TCP connection is a byte stream.	| UDP connection is message stream.|
|Overhead	| Low but higher than UDP.	| Very low.|

# Common Used Protocols

| Protocol | Function | Used Ports | Used Transport Protcol |
|:---|:---|:---:|:---:|
|FTP - File Transfer Protocol| It is a standard communication protocol used for the transfer of computer files from a server to a client on a computer network. | 21 | TCP|
|SSH - Secure Shell|It is a cryptographic network protocol for operating network services securely over an unsecured network. It's most notable applications are remote login and command-line execution. | 22 | TCP|
|TELNET - Telecommunication Network| It is a client/server application protocol that provides access with unsafe way to virtual terminals of remote systems on local area networks or the Internet. | 23 | TCP|
|SMTP - Simple Mail Transfer Network|It is an Internet standard communication protocol for electronic mail transmission. Mail servers and other message transfer agents use SMTP to send and receive mail messages. | 25 | TCP|
|DNS - Domain Name Server|It is a hierarchical and distributed naming system for computers, services, and other resources in the IP networks. It associates various information with domain names assigned to each of the associated entities. | 53 | TCP/UDP|
|DHCP - Dynamic Host Configration Protocol|It is a network management protocol used on IP networks for automatically assigning IP addresses and other communication parameters to devices connected to the network using a client–server architecture. | 67,68 | UDP|
|TFTP - Trivial File Transfer Protocol| It is a simple lockstep File Transfer Protocol which allows a client to get a file from or put a file onto a remote host. One of its primary uses is in the early stages of nodes booting from a local area network. | 69 | UDP|
|HTTP - Hypertext Transfer Protocol|It is an application layer protocol in the Internet protocol suite model for distributed, collaborative, hypermedia information systems. HTTP is the foundation of data communication for the World Wide Web, where hypertext documents include hyperlinks to other resources that the user can easily access. | 80 | TCP|
|HTTPS - Secure Hypertext Transfer Protocol|It is the secure version of HTTP, which is the primary protocol used to send data between a web browser and a website. HTTPS is encrypted in order to increase security of data transfer. | 443 | TCP|
|POP3 - Post Office Protocol|It is an application-layer Internet standard protocol used by e-mail clients to retrieve e-mail from a mail server. | 110 | TCP|
|SNMP - Simple Network Management Protocol |It is an Internet Standard protocol for collecting and organizing information about managed devices on IP networks and for modifying that information to change device behaviour. | 161,162 | TCP/UDP|

**_by wasny0ps_**

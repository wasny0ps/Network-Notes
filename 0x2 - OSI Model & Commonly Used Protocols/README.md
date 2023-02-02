# OSI Model

OSI stands for Open Systems Interconnection. It has been developed by ISO – ‘International Organization for Standardization‘, in the year 1984. It is a **7 layer architecture with each layer having specific functionality to perform**. All these 7 layers work collaboratively to transmit the data from one person to another across the globe.

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x2%20-%20OSI%20Model%20%26%20Commonly%20Used%20Protocols/source/OSI_Model.png"></p>



## Physical Layer (Layer 1)

**The lowest layer of the OSI reference model** is the physical layer. It is responsible for the actual physical connection between the devices. The physical layer contains information in the form of **bits**. It is responsible for transmitting individual bits from one node to the next. **When receiving data, this layer will get the signal received and convert it into 0s and 1s and send them to the Data Link layer, which will put the frame back together**. 

> Hub, Repeater, Modem, Cables are Physical Layer devices.


## Data Link Layer (Layer 2)

The data link layer is **responsible for the node-to-node delivery of the message**. The main function of this layer is to make sure data transfer is error-free from one node to another, over the physical layer. When a packet arrives in a network, it is the responsibility of DLL to transmit it to the Host using its **MAC address**. Data Link Layer is divided into two sublayers: 

- Logical Link Control (LLC)
* Media Access Control (MAC)

The packet received from the Network layer is further divided into frames depending on the **frame** size of **NIC(Network Interface Card)**. **DLL also encapsulates Sender and Receiver’s MAC address in the header**. 

The Receiver’s MAC address is **obtained by placing an ARP(Address Resolution Protocol)** request onto the wire asking “Who has that IP address?” and the destination host will reply with its MAC address.

> Packet in Data Link layer is referred to as **Frame**. Switch & Bridge are Data Link Layer devices.

## Network Layer (Layer 3)

The network layer works for the transmission of data from one host to the other located in different networks. **It also takes care of packet routing selection of the shortest path to transmit the packet, from the number of routes available**. **The sender & receiver’s IP addresses are placed in the header by the network layer**. The functions of the Network layer are :  

- **Routing**: The network layer protocols determine which route is suitable from source to destination. This function of the network layer is known as routing.
* **Logical Addressing**: In order to identify each device on internetwork uniquely, the network layer defines an addressing scheme. The sender & receiver’s IP addresses are placed in the header by the network layer. Such an address distinguishes each device uniquely and universally.

> **Segment** in Network layer is referred to as Packet. Network layer is implemented by networking devices such as routers. 

## Network Layer (Layer 4)

The transport layer provides services to the application layer and takes services from the network layer. The data in the transport layer is referred to as Segments. It is responsible for the End to End Delivery of the complete message. The transport layer also provides the acknowledgement of the successful data transmission and re-transmits the data if an error is found.

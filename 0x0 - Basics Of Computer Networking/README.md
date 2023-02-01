# Contents

## Computer Networking 101

**Open system**: 
A system which is connected to the network and is ready for communication. 

**Closed system**: 
A system which is not connected to the network and can’t be communicated with.

**Computer Network**: 
An interconnection of multiple devices, also known as hosts, that are connected using multiple paths for the purpose of sending/receiving data or media. Computer networks can also include multiple devices/mediums which help in the communication between two different devices; these are known as Network devices and include things such as routers, switches, hubs, and bridges.

## Network Devices
<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x0%20-%20Basics%20Of%20Computer%20Networking/sources/network_devices.png"></p>

**Hub**: Hub in networking plays a vital role in **data transmission, and broadcasting**. Hub is a hardware device used at the **physical layer** to connect multiple devices in the network. Hubs are widely used to connect **LANs(Local Area Network)**. A hub has multiple ports and **it is a non-intelligent device**. It acts as a dumb switch that does not know, which data needs to be forwarded where so it broadcasts or sends the data to each port. 

**Switch**: A network switch **connects devices in a network to each other**, enabling them to talk by exchanging data packets. Switches can be hardware devices that **manage physical networks or software-based virtual devices**. Switches form the vast majority of network devices in modern data networks. They provide the wired connections to desktop computers, wireless access points (APs), printers, industrial machinery and some internet of things devices, such as card entry systems.

A network switch **operates on Layer 2 (Data Link Layer)** of the Open Systems Interconnection (OSI) model. In a local area network (LAN) using Ethernet, a network switch determines where to send each incoming message **frame** by looking at the **media access control (MAC) address**. **Switches maintain tables that match each MAC address to the port receiving the MAC address**.

**Router**: A router is a device that **connects two or more packet-switched networks or subnetworks**. It serves two primary functions: managing traffic between these networks by forwarding data packets to **their intended IP addresses**, and allowing multiple devices to use the same Internet connection.

**Wireless Router**: Wireless routers are commonly found in homes. They're the hardware devices that Internet service providers use to connect you to their cable or xDSL Internet network. A wireless router, also called a **Wi-Fi router**, **combines the networking functions of a wireless access point and a router**.**A router connects local networks to other local networks or to the Internet**. A wireless access point connects devices to the network wirelessly.

**Bridge**: A bridge in a computer network is a device used to connect multiple LANs together with a larger Local Area Network (LAN). The mechanism of network aggregation is known as bridging. The bridge is a physical or hardware device but **operates at the OSI model’s data link layer and is also known as a layer of two switches**. 

The primary responsibility of a switch is to examine the incoming traffic and determine whether to filter or forward it.**Basically, a bridge in computer networks is used to divide network connections into sections, now each section has separate bandwidth and a separate collision domain**. Here bridge is used to **improve network performance**. 

**Wireless Bridge**: A wireless bridge is a type of networking device that **enables an over-the-air connection between two different segments of a local area network (LAN)**. **Wireless bridges use radio signals in the microwave or laser spectrum to provide fixed wireless access**. A wireless bridge, which may also be referred to as a **Wi-Fi bridge**, works much like a wired network bridge. They play an important role in connecting LAN segments that are logically separated or located in different physical locations.

Here is a simple newtork topology.

<p align="center"><img width="500px" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x0%20-%20Basics%20Of%20Computer%20Networking/sources/basic_network_topology.png"></p>


## Cabling In The Network

**End point devices**: Endpoints are **physical devices** that connect to and exchange information with a computer network. Some examples of endpoints are **mobile devices**, **desktop computers**, **firewalls**, virtual machines, embedded devices, and servers.

**Network Devices**: Network devices are physical devices that allow hardware on a computer network to interact and communicate with one another. In layman's terms, we can describe network devices in computer networks as the devices that connect fax machines, computers, printers, and other electronic devices to the network.

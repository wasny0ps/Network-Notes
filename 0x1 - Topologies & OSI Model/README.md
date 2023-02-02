# Types Of Computer Networks


**PAN**: **Personal Area Network**. It connects electronic devices within a user's immediate area. **The size of a PAN ranges from a few centimeters to a few meters**. One of the most common real-world examples of a PAN is the **connection between a Bluetooth earpiece and a smartphon**e. PANs can also connect laptops, tablets, printers, keyboards, and other computerized devices.

**WLAN**: **Wireless Local Area Network**. It is a group of colocated computers or other devices that form a network based on radio transmissions rather than wired connections. A Wi-Fi network is a type of WLAN; anyone connected to Wi-Fi while reading this webpage is using a WLAN.

**LAN**: **Local Area Network**. It is a collection of devices **connected together in one physical location**, such as a **building, office, or home**. A LAN can be small or large, ranging from a home network with one user to an enterprise network with thousands of users and devices in an office or school.

**MAN**: **Metropolitan Area Network**. **It covers a larger area than that of a LAN and smaller area as compared to WAN**. It connects two or more computers that are apart but **reside in the same or different cities**. It covers a large geographical area and may serve as an ISP (Internet Service Provider). MAN is designed for customers who need high-speed connectivity.

**WAN**: **Wide Area Network**. It is a collection of local-area networks or other networks that communicate with one another.  A WAN is essentially a network of networks, with **the Internet the world's largest WAN**. Today, there are several types of WANs, built for a variety of use cases that touch virtually every aspect of modern life.

Here is a picture about types of computer networks:

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x1%20-%20Topologies%20%26%20OSI%20Model/source/types_of_computer_networks.png"></p>

## Physical Topologies

Physical topology indicates arrangement of different elements of a network. It reflects physical layout of devices and cables to a form a connected network. It is concerned with essentials of network ignoring minute details like transfer of data and device type. The pattern of arrangement of nodes (computers) and network cables depends on ease of installation and setup of the network. It affects cost and bandwidth capacity based on solution of devices. It takes into account placement of nodes and distance between them.


Types Of Physical Topologies:

- Bus Topology
* Ring Topology
+ Star Topology
- Tree Topology
* Mesh Topology


## Bus Topology

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x1%20-%20Topologies%20%26%20OSI%20Model/source/bus_topology.png"></p>

Bus topology, also known as line topology, is a type of network topology in which all devices in the network are connected by one central **RJ-45 network cable or coaxial cable**. The single cable, where all data is transmitted between devices, is referred to as the bus, backbone, or trunk. It is bi-directional. It is a multi-point connection and a non-robust topology because if the backbone fails the topology crashes. In Bus Topology, various MAC (Media Access Control) protocols are followed by LAN ethernet connections.


| Advantage | Problems |
| :---:| :---:|
|  Adding a new device is easy.   |  Problem detection is difficult.   | 
|A broken device does not affect other devices.|A broken main network effects other devices|


## Ring Topology

<p align="center"><img height="250" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x1%20-%20Topologies%20%26%20OSI%20Model/source/ring_topology.png"></p>


In this topology, it forms a ring connecting devices with exactly two neighboring devices. A number of repeaters are used for Ring topology with a large number of nodes, because if someone wants to send some data to the last node in the ring topology with 100 nodes, then the data will have to pass through 99 nodes to reach the 100th node. Hence to **prevent data loss repeaters are used in the network**. In this topology, the **Token Ring Passing protocol** is used by the workstations to transmit the data.

| Advantage | Problems |
| :---:| :---:|
|  Device count doesn't affect network's performance.   |  The problem with the station affects the entire network.   | 


## Star Topology



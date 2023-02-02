# Types Of Computer Networks


**PAN**: **Personal Area Network**. It connects electronic devices within a user's immediate area. **The size of a PAN ranges from a few centimeters to a few meters**. One of the most common real-world examples of a PAN is the **connection between a Bluetooth earpiece and a smartphon**e. PANs can also connect laptops, tablets, printers, keyboards, and other computerized devices.

**WLAN**: **Wireless Local Area Network**. It is a group of colocated computers or other devices that form a network based on radio transmissions rather than wired connections. A Wi-Fi network is a type of WLAN; anyone connected to Wi-Fi while reading this webpage is using a WLAN.

**LAN**: **Local Area Network**. It is a collection of devices **connected together in one physical location**, such as a **building, office, or home**. A LAN can be small or large, ranging from a home network with one user to an enterprise network with thousands of users and devices in an office or school.

**MAN**: **Metropolitan Area Network**. **It covers a larger area than that of a LAN and smaller area as compared to WAN**. It connects two or more computers that are apart but **reside in the same or different cities**. It covers a large geographical area and may serve as an ISP (Internet Service Provider). MAN is designed for customers who need high-speed connectivity.

**WAN**: **Wide Area Network**. It is a collection of local-area networks or other networks that communicate with one another.  A WAN is essentially a network of networks, with **the Internet the world's largest WAN**. Today, there are several types of WANs, built for a variety of use cases that touch virtually every aspect of modern life.

Here is a picture about types of computer networks:

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x1%20-%20Topologies/source/types_of_computer_networks.png"></p>

## Physical Topologies

Physical topology indicates arrangement of different elements of a network. It reflects physical layout of devices and cables to a form a connected network. It is concerned with essentials of network ignoring minute details like transfer of data and device type. The pattern of arrangement of nodes (computers) and network cables depends on ease of installation and setup of the network. It affects cost and bandwidth capacity based on solution of devices. It takes into account placement of nodes and distance between them.


Types Of Physical Topologies:

- Bus Topology
* Ring Topology
+ Star Topology
- Mesh Topology
* Tree Topology


## Bus Topology

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x1%20-%20Topologies/source/bus_topology.png"></p>

Bus topology, also known as line topology, is a type of network topology in which all devices in the network are connected by one central **RJ-45 network cable or coaxial cable**. The single cable, where all data is transmitted between devices, is referred to as the bus, backbone, or trunk. It is bi-directional. It is a multi-point connection and a non-robust topology because if the backbone fails the topology crashes. In Bus Topology, various MAC (Media Access Control) protocols are followed by LAN ethernet connections.


| Advantage | Problems |
| :---:| :---:|
|  Adding a new device is easy.   |  Problem detection is difficult.   | 
|A broken device does not affect other devices.|A broken main network effects other devices|


## Ring Topology

<p align="center"><img height="250" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x1%20-%20Topologies/source/ring_topology.png"></p>


In this topology, it forms a ring connecting devices with exactly two neighboring devices. A number of repeaters are used for Ring topology with a large number of nodes, because if someone wants to send some data to the last node in the ring topology with 100 nodes, then the data will have to pass through 99 nodes to reach the 100th node. Hence to **prevent data loss repeaters are used in the network**. In this topology, the **Token Ring Passing protocol** is used by the workstations to transmit the data.

| Advantage | Problems |
| :---:| :---:|
|  Device count doesn't affect network's performance.   |  The problem with the station affects the entire network.   | 


## Star Topology

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x1%20-%20Topologies/source/star_topology.png"></p>

In star topology, all the devices are **connected to a single hub** through a cable. This hub is the central node and all other nodes are connected to the central node. The hub can be passive in nature i.e., not an intelligent hub such as broadcasting devices, at the same time the hub can be intelligent known as an active hub. Active hubs have repeaters in them. Coaxial cables or RJ-45 cables are used to connect the computers.

| Advantage | Problems |
| :---:| :---:|
|  Adding a new device is easy.  |  Requires a lot of cables.  | 
|Problem detetection is snap. |If the concentrator (hub) on which the whole topology relies fails, the whole system will crash down.|


## Mesh Topology

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x1%20-%20Topologies/source/mesh_topology.png"></p>


In a mesh topology, every device is connected to another device via a particular channel. 

| Advantage | Problems |
| :---:| :---:|
|  Communication is very fast between the nodes.  |  The cost of cables is high as bulk wiring is required, hence suitable for less number of devices.  | 
|Data is reliable because data is transferred among the devices through dedicated channels or links. |The cost of maintenance is high.|
|Provides security and privacy.| Installation and configuration are difficult.|


## Tree Topology

<p align="center"><img width="500" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x1%20-%20Topologies/source/tree-topology.png"></p>

In computer networking, tree topology is a type of network topology that **resembles a tree**. In a tree topology, there is one central node (the **trunk**), and each node is connected to the central node through a single path. Nodes can be thought of as branches coming off of the trunk. Tree topologies are often used to create large networks.

| Advantage | Problems |
| :---:| :---:|
|  Error detection and error correction are very easy.  |  If the central hub gets fails the entire system fails.  | 
|We can add new devices to the existing network. |The cost is high because of the cabling.|
|It allows the network to get isolated and also prioritize from different computers.| If new devices are added, it becomes difficult to reconfigure.|


**_by wasny0ps_**

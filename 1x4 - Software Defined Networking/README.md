# Software Defined Networking (SDN)

<p align="center"><img height="350" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x4%20-%20Software%20Defined%20Networking/src/SDN.png"></p>

SDN stands for Software Defined Networking which is a networking architecture approach. It **enables the control and management of the network using software applications**. **Through Software Defined Network (SDN) networking behavior of the entire network and its devices are programmed in a centrally controlled manner through software applications using open APIs**. 

Generally, **enterprises use SDN**, the most widely used method for application deployment, to deploy applications faster while lowering overall deployment and **operating costs**. **SDN allows IT administrators to manage and provision network services from a single location**. And, cloud networking software-defined uses white-box systems. cloud providers often use generic hardware so that the cloud data center can be changed and the cost of **CAPEX and OPEX** saved. To understand software-defined networks, we need to understand the various **planes involved in networking**:

- **Data plane:** All the activities involving as well as resulting from data packets sent by the end-user belong to this plane. This includes:
  
   - **Forwarding of packets**.
   - **Segmentation and reassembly of data**.
   - **Replication of packets for multicasting**. 

- **Control plane:** All activities necessary to perform data plane activities but do not involve end-user data packets belong to this plane. In other words, this is the **brain of the network**. The activities of the control plane include:
  
   - **Making routing tables**.
   - **Setting packet handling policies**.


## Why SDN is Important?

- **Better Network Connectivity:** SDN provides very better network connectivity for sales, services, and internal communications. SDN also **helps in faster data sharing**.
- **Better Deployment of Applications:** Deployment of new applications, services, and many business models can be speed up using Software Defined Networking.
- **Better Security:** Software-defined network **provides better visibility throughout the network**. Operators can **create separate zones for devices that require different levels of security**. SDN networks **give more freedom to operators**.
- **Better Control with High Speed:** Software-defined networking **provides better speed than other networking types by applying an open standard software-based controller**.

In short, it can be said that **SDN acts as a “Bigger Umbrella or a HUB”** where the rest of other networking technologies come and sit under that umbrella and get merged with another platform to bring out the best of the best outcome by decreasing the traffic rate and by increasing the efficiency of data flow.

### Advantages of SDN

- The network is **programmable** and hence can **easily be modified via the controller rather than individual switches**.
- **Switch hardware becomes cheaper** since each switch only needs a data plane.
- Hardware is abstracted, hence applications can be written on top of the controller independent of the switch vendor.
- Provides better security since the controller can **monitor traffic** and **deploy security policies**. For example, if the controller detects suspicious activity in network traffic, it can reroute or drop the packets.

### Disadvantages of SDN

- The central dependency of the network means a **single point of failure**, if the controller gets corrupted, the entire network will be affected.
- The use of SDN **on large scale is not properly defined and explored**.


## Difference Between SDN & Traditional Networking

|Software Defined Networking|Traditional Networking|
|-|-|
|Software Defined Network is a **virtual networking** approach.|A traditional network is the **old conventional networking** approach.|
|Software Defined Network is **centralized control**.|Traditional Network is **distributed control**.|
|This network is **programmable**.|This network is **nonprogrammable**.|
|Software Defined Network is the **open interface**.|A traditional network is a **closed interface**.|
|In Software Defined Network data plane and control, the plane is decoupled by software.|In a traditional network data plane and control plane are mounted on the same plane.|

## Components of Software Defined Networking (SDN)

<p align="center"><img height="300" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x4%20-%20Software%20Defined%20Networking/src/SDN_components.png"></p>

The three main components that make the SDN are:
- **SDN Applications:** SDN Applications relay requests or networks through SDN Controller using API.
- **SDN controller:** SDN Controller collects network information from hardware and sends this information to applications. 
- **SDN networking devices:** SDN Network devices help in forwarding and data processing tasks.


## SDN Controller

All traditional networking devices like router and switches uses distributed control plane. But newer model of networking, **Software Defined Networking (SDN) uses centralized control plane**. Distributed control plane means that control plane of all networking devices lies within the device itself. 

Each device have their own control plane to control data plane. In centralized control plane system, there is a device which contains control plane of all devices. This device control the activities of data plane of all networking devices simultaneously. This device is called **controller or SDN controller**. The following figure shows a model of controller based networking. 

<p align="center"><img height="300" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x4%20-%20Software%20Defined%20Networking/src/SDN_controller.png"></p>


#### Southbound Interface

In SDN, all networking devices must be connected to controller so that it can **regulate data planes of all devices**. When drawing architecture of network, usually the network architect places networking devices below controller. Now according to map conventions, interface between controller and networking devices lies to south of controller. Hence, these interfaces are called Southbound Interface. 

**Southbound interface is an interface between a program on controller and a program on networking device**. Note that these interfaces we are discussing are software interface **not physical** one. There is some alternativies for using southbound interface such as:

- **OpenFlow**
- **Cisco OpFlex**
- **CLI**

#### OpenFlow

<p align="center"><img height="350" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x4%20-%20Software%20Defined%20Networking/src/openflow.png"></p>

OpenFlow is a communication protocol and the basic component of the software-defined networking structure located in the network control and routing regions. SDN creates network intelligence and admin center in software controllers that maintain the global view of the network. Currently, OpenFlow is the **only open standards-based protocol for communicating between an SDN controller and network details**. **It enables direct programming of network hardware such as both physical and virtual switches and external agents to make networks more dynamic, manageable, slower speeds and alert**.

An important feature of OpenFlow is that **it uses streams to define network traffic based on predefined matching rules that can be programmed statically or dynamically using SDN control software**. In simpler terms, OpenFlow **transmits information from a controller to switches and tells them what to do**. In turn, switches provide counters and other data to the controller.

Because it works on flows, OpenFlow provides granular control of IT to respond to real-time changes in application, user, and session levels. OpenFlow allows IT to define how traffic should flow through the network based on factors such as usage patterns, application requirements, service level agreements, and cloud resources.

#### Cisco Opflex

OpFlex is a southbound protocol in a software-defined network (SDN) designed for communications between the SDN Controller and the infrastructure (switches and routers). The keyword here is **“Multi-vendor environment”** – i.e. Openflow designed to support all the vendor networking devices. The goal is to create a standard that enables policies to be applied across physical and virtual switches/routers in a multi-vendor environment.

#### Northbound Interface

<p align="center"><img height="250" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x4%20-%20Software%20Defined%20Networking/src/northbound.png"></p>

Controller need to know many information regarding network so that it can control data plane of networking devices All these information are provided by network programmer. network programmer provide essential information to controller through various software or script about what functions it has to do. Again these softwares/scripts are placed above controller in network architecture. This placement of software/script makes interfaces between controller and software in north direction, according to map conventions. Hence, Interfaces between controller and softwares are called Northbound Interface. These interfaces enable programmability of network. 
All interfaces we discussed above are program based interfaces. These interfaces in a broader sense are called Application Program Interface (API). An API is an interface through which two program can exchange data between them.

Numerous applications via API SDN controller can access:
- Information about the network from the SDN controller GUI can be used to retrieve it.
- Command written in Java or Python files, information from SDN controller to get or configure the network can use the API.

## SDN Architecture

<p align="center"><img height="350" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x4%20-%20Software%20Defined%20Networking/src/SDN_architecture.png"></p>


In a traditional network, each switch has its own data plane as well as the control plane. The control plane of various switches exchange topology information and hence construct a forwarding table that decides where an incoming data packet has to be forwarded via the data plane. Software-defined networking (SDN) is an approach via which we take the control plane away from the switch and assign it to a centralized unit called the SDN controller. Hence, a network administrator can shape traffic via a centralized console without having to touch the individual switches. The data plane still resides in the switch and when a packet enters a switch, its forwarding activity is decided based on the entries of flow tables, which are pre-assigned by the controller. A flow table consists of match fields (like input port number and packet header) and instructions. The packet is first matched against the match fields of the flow table entries. Then the instructions of the corresponding flow entry are executed. The instructions can be forwarding the packet via one or multiple ports, dropping the packet, or adding headers to the packet. If a packet doesn’t find a corresponding match in the flow table, the switch queries the controller which sends a new flow entry to the switch. The switch forwards or drops the packet based on this flow entry. 

A typical SDN architecture consists of three layers.

- **Application layer:** It contains the typical network applications like intrusion detection, firewall, and load balancing.
- **Control layer:** It consists of the SDN controller which acts as the brain of the network. It also allows hardware abstraction to the applications written on top of it.
- **Infrastructure layer:** This consists of physical switches which form the data plane and carries out the actual movement of data packets.

The layers communicate via a set of interfaces called the north-bound APIs(between the application and control layer) and southbound APIs(between the control and infrastructure layer). 

## Different Models of SDN

There are several models, which are used in SDN:

- Open SDN
- SDN via APIs
- SDN via Hypervisor-based Overlay Network
- Hybrid SDN

### Open SDN

<p align="center"><img height="350" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x4%20-%20Software%20Defined%20Networking/src/open_sdn.png"></p>

Open SDN is implemented using the OpenFlow switch. It is a straightforward implementation of SDN. In Open SDN, the controller communicates with the switches using south-bound API with the help of OpenFlow protocol.

### SDN via APIs

<p align="center"><img height="350" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x4%20-%20Software%20Defined%20Networking/src/SDN_APIs.png"></p>


In SDN via API, the functions in remote devices like switches are invoked using conventional methods like SNMP or CLI or through newer methods like Rest API. Here, the devices are provided with control points enabling the controller to manipulate the remote devices using APIs. 

### SDN via Hypervisor-based Overlay Network

<p align="center"><img height="350" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x4%20-%20Software%20Defined%20Networking/src/SDN_supervisor.png"></p>

In SDN via the hypervisor, the configuration of physical devices is unchanged. Instead, Hypervisor based overlay networks are created over the physical network. Only the devices at the edge of the physical network are connected to the virtualized networks, thereby concealing the information of other devices in the physical network.

### Hybrid SDN

<p align="center"><img height="350" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x4%20-%20Software%20Defined%20Networking/src/hybrid_SDN.png"></p>

Hybrid Networking is a combination of Traditional Networking with software-defined networking in one network to support different types of functions on a network.

**_by wasny0ps_**


# Software Defined Networking (SDN)

<p align="center"><img height="400" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x4%20-%20Software%20Defined%20Networking/src/SDN.png"></p>

SDN stands for Software Defined Network which is a networking architecture approach. It **enables the control and management of the network using software applications**. **Through Software Defined Network (SDN) networking behavior of the entire network and its devices are programmed in a centrally controlled manner through software applications using open APIs**. 

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

- The network is programmable and hence can easily be modified via the controller rather than individual switches.
- Switch hardware becomes cheaper since each switch only needs a data plane.
- Hardware is abstracted, hence applications can be written on top of the controller independent of the switch vendor.
- Provides better security since the controller can monitor traffic and deploy security policies. For example, if the controller detects suspicious activity in network traffic, it can reroute or drop the packets.

### Disadvantages of SDN

- The central dependency of the network means a single point of failure, i.e. if the controller gets corrupted, the entire network will be affected.
- The use of SDN on large scale is not properly defined and explored.


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

## SDN Applications

## SDN Controller


## SDN Architecture


## Different Models of SDN

### Open SDN

### SDN via APIs

### SDN via Hypervisor-based Overlay Network

### Hybrid SDN

## Mininet Topology Configuration



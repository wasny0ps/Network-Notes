
# Computer Networking 101

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

**Straight Cabling**: A straight through cable is a type of **twisted pair cable** that is used in local area networks to connect a computer to a network **hub** such as a **router**.

Use straight through Ethernet cable for the following cabling:
- Switch to router
* Switch to PC or server
+ Hub to PC or server

<p align="center"><img width="500px" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x0%20-%20Basics%20Of%20Computer%20Networking/sources/straight-through-cable.png"></p>

**Cross Cabling**: A crossover Ethernet cable is a type of **Ethernet cable** used to connect computing devices together directly. Unlike straight through cable, the RJ45 crossover cable uses two different wiring standards: one end uses the **T568A wiring standard**, and the other end uses the **T568B wiring standard**. The internal wiring of Ethernet crossover cables reverses the transmit and receive signals. It is most often used to connect two devices of the same type: e.g. two **computers or two switches to each other**.

Use crossover cables for the following cabling:
- Switch to switch
* Switch to hub
+ Hub to hub
- Router to router
* PC to PC

<p align="center"><img width="500px" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x0%20-%20Basics%20Of%20Computer%20Networking/sources/crossover-cable.png"></p>

## Cable Types

**Fiber Optic Cable**: Fiber optic cable, also know as optical fiber cable, is a **type of Ethernet cable** which consists of one or more optic fibers that are used to transmit data. It is an assembly similar to an **electrical cable** while it is used to carry light and the **fiber optic cable price is much higher than that of copper cable**. Designed to use light pulses, fiber optic cables **support long distance telecommunication and high-speed data transmission**. Normally, fiber optic cable can run at a speed of 10 Gbps, 40 Gbps and even 100 Gbps. Therefore, it is widely used in much of the world’s internet, cable television and telephone systems.

**Coaxial Cable**: A coaxial cable is an electrical cable with a copper conductor and an insulator shielding around it and a braided metal mesh that prevents signal interference and cross talk. Coaxial cable is also known as **coax**.

**The core copper conductor** is used for the transmission of signals and the insulator is used to provide insulation to the copper conductor and the insulator is surrounded by a braided metal conductor which helps to **prevent the interference of electrical signals and prevent cross talk**. **This entire setup is again covered with a protective plastic layer to provide extra safety to the cable**.

**UTP Cable**: Short for **unshielded twisted pair**, a UTP cable is a cable used in computer networking that consists of two shielded wires twisted around each other. As the name would imply, these cables do not have insulation (shielding) between each of the paired wires. Consequently, **they do not block electromagnetic interference, resulting in a higher risk of packet loss or corruption**.


**_by wasny0ps_**

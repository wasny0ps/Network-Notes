# Dynamic Routing

Dynamic routing is when protocols, called routing protocols, are used to build the routing tables across the network. Using a routing protocol is easier than static routing and default routing, but it is more expensive in terms of CPU and bandwidth usage. Every routing protocol defines its own rules for communication between routers and selecting the **best route**.

- There are few dynamic routing protocols: **RIP, OSPF, BGP, EIGRP**

## Routing Information Protocol (RIP)

<img margin="center" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x8%20-%20Dynamic%20Routing/src/rip.png">

RIP is a dynamic routing protocol that uses **hop count as a routing metric** to find the best path between the source and the destination network. It is a **distance-vector routing protocol that has an AD value of 120** and works on the Network layer of the OSI model.

#### Hop Count

Hop count is the **number of routers occurring in between the source and destination network**. The path with the **lowest hop count is considered as the best route** to reach a network and therefore placed in the routing table. **RIP prevents routing loops by limiting the number of hops allowed in a path from source and destination**. The maximum hop count allowed for RIP is 15 and a hop count of 16 is considered as network unreachable. 

## Features of RIP

- Updates of the network are exchanged periodically.
- **Updates (routing information) are always broadcast**. 
- **Full routing tables are sent in updates**. 
- Routers always trust routing information received from neighbor routers. This is also known as Routing on rumors. 

## RIP Versions

As time progressed, the class structure of the network could not meet the need and the subnet system was started. For this reason, three versions of routing information protocol were born: RIP Version1, RIP Version2, and RIPng. 

|RIPv1|RIPv2|RIPng|
|-|-|-|
|Sends update as broadcast|Sends update as multicast|Sends update as multicast|
|Broadcast at 255.255.255.255|Multicast at 224.0.0.9|Multicast at FF02::9 (RIPng can only run on IPv6 networks)|
|Doesn’t support authentication of updated messages|Supports authentication of RIPv2 update messages|-|
|Classful routing protocol|Classless protocol updated supports classful|Classless updates are sent|

- **RIP v1 is known as Classful Routing Protocol because it doesn’t send information of subnet mask in its routing update**. 
- **RIP v2 is known as Classless Routing Protocol because it sends information of subnet mask in its routing update**. 


## Open Shortest Path First (OSPF)

It is a protocol developed by IETF (Internet Engineering Task Force) to improve and correct some deficiencies in the RIP protocol. **Unlike RIP, OSPF was designed as a Link-state protocol**. **Link-state routing protocols can see the entire topology as well as send a Triggered update on network images**. Accordingly, after the samples reach the information of all the routes between two points in the network, they **decide which route is the best by using SPF (Shortest Path First) examinations**. **Also known as Link-state Refresh, it sends updates every 30 minutes**.

The most important feature of the OSPF protocol that makes it different from other protocols is that it is a **line status protocol**. Accordingly, OSPF is very successful in **learning path information quickly**, **working better in large and complex networks**, and **reliability**. In addition, OSPF has other features besides these important features.
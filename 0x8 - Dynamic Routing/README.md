# Dynamic Routing

Dynamic routing is when protocols, called routing protocols, are used to build the routing tables across the network. Using a routing protocol is easier than static routing and default routing, but it is more expensive in terms of CPU and bandwidth usage. Every routing protocol defines its own rules for communication between routers and selecting the **best route**.

- There are few dynamic routing protocols: **RIP, OSPF, BGP, EIGRP**

## Routing Information Protocol (RIP)

<p align="center"><img width="400" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x8%20-%20Dynamic%20Routing/src/rip.png"></p>

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

## RIP Configration

Here is my uncured topology look like. Let's configrate!

<p align="center"><img  src="https://github.com/wasny0ps/Network-Notes/blob/main/0x8%20-%20Dynamic%20Routing/src/rip_topology.png"></p>

Assign IPs into router's interfaces.
- Router0:

```
R0(config)#interface gigabitEthernet 0/0/0
R0(config-if)#ip ad 192.168.1.1 255.255.255.192
R0(config-if)#no shut
R0(config-if)#ex
R0(config)#interface se0/1/0
R0(config-if)#ip ad 85.0.0.1 255.0.0.0
R0(config-if)#no shut
```
- Router1:

```
R1(config)#interface gigabitEthernet 0/0/0
R1(config-if)#ip ad 192.168.1.65 255.255.255.192
R1(config-if)#no shut
R1(config-if)#ex
R1(config)#interface se0/1/0
R1(config-if)#ip ad 86.0.0.1 255.0.0.0
R1(config-if)#no shut
R1(config-if)#ex
R1(config)#interface se0/1/1
R1(config-if)#ip ad 85.0.0.2 255.0.0.0
R1(config-if)#no shut
```

- Router2:

```
R2(config)#interface gigabitEthernet 0/0/0
R2(config-if)#ip ad 192.168.1.129 255.255.255.192
R2(config-if)#no shut
R2(config-if)#ex
R2(config)#in
R2(config)#interface se0/1/1
R2(config-if)#ip ad 86.0.0.2 255.0.0.0
R2(config-if)#no shut

```

After assigning IP addresses, we must set the RIP protocol. In this step, you should enter the networks which are directly connected to router's interfaces use for introducing network to other routers. Also, in this example, the network has classful structure because of the subnetting. Thats's why, we use `version 2` command. What is more, if you wonder about why we use `no auto-summary` command, you may draw on this [link](https://community.cisco.com/t5/switching/what-is-the-use-of-no-auto-summary-command/td-p/1340409).

- Router0:
```
R0(config)#router rip
R0(config-router)#network 192.168.1.0
R0(config-router)#network 85.0.0.0
R0(config-router)#version 2
R0(config-router)#no auto-summary 
```

- Router1:

```
R1(config)#router rip
R1(config-router)#network 192.168.1.64
R1(config-router)#network 85.0.0.0
R1(config-router)#network 86.0.0.0
R1(config-router)#version 2
R1(config-router)#no auto-summary 
```

- Router2:

```
R2(config)#router rip
R2(config-router)#network 192.168.1.128
R2(config-router)#network 86.0.0.0
R2(config-router)#version 2
R2(config-router)#no auto-summary 
```

And, you can check your configration like this command.

```
R1#show ip route rip 
     192.168.1.0/24 is variably subnetted, 4 subnets, 2 masks
R       192.168.1.0/26 [120/1] via 85.0.0.1, 00:00:06, Serial0/1/1
R       192.168.1.128/26 [120/1] via 86.0.0.2, 00:00:05, Serial0/1/0

```

You can download this example [here](https://github.com/wasny0ps/Network-Notes/blob/main/0x8%20-%20Dynamic%20Routing/src/RIP.pkt).

## Open Shortest Path First (OSPF)



<p align="center"><img width="400" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x8%20-%20Dynamic%20Routing/src/ospf.png"></p>


It is a protocol developed by IETF (Internet Engineering Task Force) to improve and correct some deficiencies in the RIP protocol. **Unlike RIP, OSPF was designed as a Link-state protocol**. **Link-state routing protocols can see the entire topology as well as send a Triggered update on network images**. Accordingly, after the samples reach the information of all the routes between two points in the network, they **decide which route is the best by using SPF (Shortest Path First) examinations**. **Also known as Link-state Refresh, it sends updates every 30 minutes**.

The most important feature of the OSPF protocol that makes it different from other protocols is that it is a **line status protocol**. Accordingly, OSPF is very successful in **learning path information quickly**, **working better in large and complex networks**, and **reliability**. In addition, OSPF has other features besides these important features.

- It provides **more effective addressing** because it supports **VLSM (Variable Length Subnet Masking)** and **Supernetting**.
- It has **classless structure**.
- It ensures that the load received on the network is shared equally on the servers (**Load Balancing**). Thus, performance gain is achieved.
- The **AD (Administrative Distance) value is 110**.
- The Area value is important in the OSPF protocol. In large networks, **the size of the routing table and the complexity of the network can be reduced by dividing it into zones**.

The OSPF protocol does not use metrics like distance vector protocols. So **there is no limit on the number of digits**. It uses values that are inversely proportional to the **bandwidth** in the metric calculation. **The best route is the lowest cost route**, and the best routes are included in the routing table.

### OSPF Working Structure

<p align="center"><img width="400" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x8%20-%20Dynamic%20Routing/src/ospf_structure.png"></p>

OSPF generates an update packet whenever there is a change in the network. **When the state of a link changes, the router that detects it broadcasts a packet called LSA** (Link-State Advertisement). The LSA packet is forwarded to all neighbors. **Each router device receives a copy of the LSA, updates the LSDB (Link-State Database) and forwards the LSA to neighboring routers**. Thanks to this LSA sent, the whole network detects the change in the network and reflects it to the new topology. **LSDB is used to calculate the best path to the destination network**.

There are **3 types of tables in OSPF**. These are **Neighborhood Table**, **Topology Table** and **Routing Table**.

- The neighborhood table keeps a list of the router's neighbors.
- The topology table is known as LSDB. All routers and their connections in the network are kept. LSAs are included in this table, and most importantly, the LSDB of each router in the network must be identical.
- The routing table is also called the routing database. The information of the shortest paths to the destination networks is kept in this table.


In Multi-Access networks, a router called **DR (Designated Router) is selected that will manage all the traffic in the environment and provide communication**. In addition, a **backup router called BDR (Backup Designated Router) is selected as a backup of the DR**. DR and BDR selections are made with Router IDs. **Router ID is the highest IP address on a router's active interfaces**. However, if any loopback address is defined in this network, the ID of that router is the loopback IP.


LSA packets are started to be sent according to the responses to the **Hello packets** in the OSPF protocol. LSA packets contain routers' connections, interfaces and line status information. **Each router that exchanges LSA packets has its own LSA table, and this created LSA table is sent to other routers, creating a database where all routers in the network learn each other's LSA table**. Thanks to this created database, the route information and distance in the network are calculated. With the help of the SPF algorithm, the network topology is extracted and this process is performed again **every 30 minutes**. If there is no change on the network, no updates are made and no traffic is generated on the network, except for Hello packets.

## OSPF Configration

## RIP vs OSPF


|RIP|OSPF|
|-|-|
|RIP works on the Bellman-Ford algorithm|OSPF works on Dijkstra algorithm|
|It is a Distance Vector protocol and it uses the distance or hops count to determine the transmission path|It is a link-state protocol and it analyzes different sources like the speed, cost and path congestion while identifying the shortest path|
|It is used for smaller size organizations|It is used for larger size organizations in the network|
|It allows a maximum of 15 hops|There is no such restriction on the hop count|
|It is not a more intelligent dynamic routing protocol|It is a more intelligent routing protocol than RIP|
|Its administrative distance is 120|Its administrative distance is 110|
|RIP uses UDP Protocol|OSPF works for IP Protocol|
|It calculates the metric in terms of Hop Count|It calculates the metric in terms of bandwidth|
|In RIP, the whole routing table is to be broadcasted to the neighbors every 30 seconds by the routers|In OSPF, parts of the routing table are only sent when a change has been made to it|
|RIP utilizes less memory compared to OSPF but is CPU intensive like OSPF|OSPF device resource requirements are CPU intensive and memory|
|Its multicast address is 224.0.0.9|OSPF’s multicast addresses are 224.0.0.5 and 224.0.0.6|


**_by wasny0ps_**

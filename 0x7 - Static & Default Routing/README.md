# Routing

**The routers store receives the data packets and look for the destination Internet protocol (IP) address**. Once the IP address or network of the destination is known, the router checks the **routing table** to select the **best route** through which the packet can be transferred. The best route is selected based on the administrative distance and various cost metrics like bandwidth, congestion, and speed of the cable etc. To be able to route a packet, a router must know at least the following :

- Destination address to where the packet is destined. Layer 3 protocols such an IP take care of this.
- Neighboring routers from which remote networks can be learned of and packets can be moved to on way to its destination.
- Routes to remote networks and a way to determine the best route to each of them.
- Way to learn, verify and manage routing information. Incomplete, incorrect or unstable routing information is worse than not having any routing information. If a router does not have routing information, it will drop the packets and let the source know. If a router has incorrect routing information, loops can form and bring down networks.

Each route is a combination of the destination network address, subnet mask and the next hop towards the destination. There are three ways for a router to learn routes:

- **Static Routing** : This is the method by which an administrator **manually adds routes to the routing table of a router**. This is a method for **small networks** but it is not scalable for larger networks.

- **Default Routing** : This is the method where **all routers are configured to send all packets towards a single router**.  This is a very useful method for small networks or for networks with a single entry and exit point. 

- **Dynamic Routing** : This is the method where protocols and algorithms are used to **automatically propagate routing information**. This is the **most common method and most complex method of routing**. 

## Static Routing

When you manually add routes to the routing table, it is called static routing. There are advantages and disadvantages in using static routing. The advantages are:

- There is no overhead in terms of CPU usage of the router as well as bandwidth between routers. When dynamic routing is used, packets are exchanged between routers and that uses bandwidth. That can be costly when they traverse across WAN links. The routers also need to process these packets and that **consumes some CPU cycles as well**.

- It adds a certain degree of security since the administrator controls which routes the routers can know and learn.

The disadvantages of static routing are:

- The administrator needs to know the internetwork so well that he/she knows where each destination network lies and which is the next hop towards it.

- Every change needs to be manually done on each router in the internetwork.

- In large networks this can be **unmanageable**.

## Example Of Static Routing

At the starting point of static routing is connect end point devices to network devices. Here is my example topology.

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x7%20-%20Static%20%26%20Default%20Routing/source/static_routing_start.png" ></p>

##  Configure The Routers And Devices
First of all, we need three different IP blocks so that the routers can communicate with the local networks and the routers with each other. My IP blocks are **192.168.10.0/24**, **192.168.20.0/24**, **192.168.30.0/24**. Then, we must assign IP and subnet mask to all devices. If you don't know how to configrate routers and devices you can learn from [here](https://github.com/wasny0ps/Network-Notes/tree/main/0x5%20-%20Router%20%26%20Switch%20Configration).

After configration, my configrated topology looks like this.

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x7%20-%20Static%20%26%20Default%20Routing/source/first_conf.png" ></p>

Before manually configure routers for teach foreign networks, you should check if you give correct ip address and subnet mask to router's leg in 192.168.30.0/24 network or not. This picture is taken when hadn't give ip addresses in 192.168.30.0/24 network. Please be careful.


## Manually Teach Networks

You can teach foreign networks to both routers with `ip route -foreign network IP adress- -foreign network subnet mask- -ip address of the leg of the router to be routed in that network-` command in global configuration mode.

<img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x7%20-%20Static%20%26%20Default%20Routing/source/r1.png" >
<img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x7%20-%20Static%20%26%20Default%20Routing/source/r2.png" >


## Default Routing

Default routing can be considered a special type of static routing. The difference between a normal static route and a default route is that a default route is used to send packets destined to any unknown destination to a single next hop address. To understand how this works, let's suppose that we have two routers call Router1 and Router2. Router1 is directly connected with 192.168.1.1 IP's leg to 192.168.1.0/24 network and there is any static routes in it. When it receives a packet destined to 192.168.5.0/24 it will drop it since it does not know where the destination network is. If a default route is added in Router1 with next hop address of Router2, all packets destined to any unknown destination, such as 192.168.5.0/24 will be sent to Router2.

Default routes are useful when dealing with a network with a single exit point. It is also useful when a bulk of destination networks have to be routed to a single next-hop device. When adding a default route, you should ensure that the next-hop device can route the packet further, or else the next hop device will drop the packet.

Another point to remember is that when a more specific route to a destination exists in the routing table, the router will use that route and not the default route. The only time the router will use the default route is when a specific route does not exist.


## Dynamic Routing

Dynamic routing is when protocols, called routing protocols, are used to build the routing tables across the network. Using a routing protocol is easier than static routing and default routing, but it is more expensive in terms of CPU and bandwidth usage. Every routing protocol defines its own rules for communication between routers and selecting the best route.


**_by wasny0ps_**

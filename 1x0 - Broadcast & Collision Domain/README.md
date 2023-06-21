# What Is Domain?

A domain is a **type of computer network** in which all user computers, printers accounts, and other devices registered. **It is a central database located on single or multiple clusters of central computers, that is known as domain controllers**.

## Collision Domain

<p align="center"><img height="400" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x0%20-%20Broadcast%20%26%20Collision%20Domain/src/collision_domain.gif"/></p>

A collision domain is, as the name implies, the part of a network where packet collisions can occur. A collision occurs when two devices send a packet at the same time on the shared network segment. The packets collide and both devices must send the packets again, which reduces network efficiency. Collisions are often in a hub environment because each port on a hub is in the same collision domain. By contrast, each port on a bridge, a switch, or a router is in a separate collision domain.

<p align="center"><img height="300" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x0%20-%20Broadcast%20%26%20Collision%20Domain/src/collision_domain_example.png"/></p>

Here is an example topology. as is also understood from the picture, we have 7 collision domain in this topology. Let's explain more detail why they are collision domain or not.

- **1st and 7th domain's devices are connected to the hub**. Shortly, hubs are stupid devices. They don't switching. For this reason, **packets can receive other hub interfaces**. So **this area is accepted as one collision domain**.

<p align="center"><img height="300" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x0%20-%20Broadcast%20%26%20Collision%20Domain/src/hub.gif"/></p>

- Devices in the 2nd, 3rd and 6th domains connect to the router. **Routers don't pass the packets to other networks**. So, **every connection between network devices and router or end-user devices and router points to a collision domain**.
- And 4th and 5th fields connect to the switch. **Switches cut off network traffics between its interfaces**. So, **every connection connects with a switch kind of collision domain**.


## Advantage Of Collision Domain
- **High Network Performance:** Collision Domain helps to improve network performance by reducing collisions on the network, which can improve data transmission and reduce packet loss.
- **Efficient Use of Network Resources:** Collision Domain enables efficient use of network resources, such as bandwidth, by reducing the number of collisions and avoiding wastage of network resources.
- **Better Network Security:** Collision Domain can help to improve network security by reducing the risk of unauthorized access and network attacks, which can occur due to network congestion.

## Disadvantage Of Collision Domain
- **Limited Scalability:** Collision Domain may not be scalable in larger networks, as the number of devices connected to the network increases, which can lead to network congestion and performance degradation.
- **Complex Network Management:** Collision Domain can be complex to manage, requiring the use of protocols such as Carrier Sense Multiple Access with Collision Detection (CSMA/CD), which can be difficult to configure and maintain.

  ## Broadcast Domain

  <p align="center"><img height="400" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x0%20-%20Broadcast%20%26%20Collision%20Domain/src/broadcast_domain.gif"/></p>


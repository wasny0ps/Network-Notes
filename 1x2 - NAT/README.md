# NAT

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/1x2%20-%20NAT/src/NAT.gif"></p>

**Since the number of IPs brought by IPv4 in the world was insufficient, an IP converter mechanism was needed**. From this mechanism, users were expected to divide their IP addresses into two as local network IP and global network IP. As a result, NAT technology has entered our lives. Network Address Translation (NAT) is a service that enables private IP networks to use the internet and cloud. **NAT translates private IP addresses in an internal network to a public IP address before packets are sent to an external network**.

There is **three types of NAT soluotions** in network:
- **Static NAT**
- **Dynamic NAT**
- **Overload NAT (PAT)**

## Static NAT

A static network address translation (static NAT) is a type of NAT technique that routes and maps network traffic from a static public IP address to an internal private IP address and/or network. It enables providing external network or Internet connectivity to computers, servers or networking devices within a private local area network (private LAN) having an unregistered private IP address.

A **static NAT is primarily used in enterprise networks** where many internal servers have unregistered IP addresses and are accessed by a global audience using static public IP addresses. It provides a means to **ensure network transparency**, **security and privacy by hiding the details of internal network usage**, architecture and patterns from external or public users.

A static NAT works by **creating a one-to-one relationship between the public and private IP address**. This means the **private IP address can be mapped to only one public IP address at a time**. So, **no address pools are necessary** in the static NAT. The end user, on the other hand, has a transparent view of the remote device/network and accesses it using the mapped public IP address.

## Static NAT Configuration

To configure static NAT, three steps are required:

- Configure private/public IP address mapping by using the `ip nat inside source static PRIVATE_IP  PUBLIC_IP` command. In this step, we are **mapping manually to the devices's public IP address with its private IP address which is used on the local network**.
- Configure the router’s inside interface using the `ip nat inside` command. In other words, we are **setting which router's inside interface is connected to the local network**.
- Configure the router’s outside interface using the `ip nat outside` command. Finally, we are **assigning which router's outside interface is open to the global network**.

Here is an example topology of static NAT. Let's configure it!

<p align="center"><img height="250" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x2%20-%20NAT/src/staticnat_topology.png"></p>

Computers request a web resource from the server. Computers use their private IP address when sending the request to router. Router receives the request, changes the private IP address to the public one, and sends the request to the server. Server responds to router. Router receives the response, looks it up in its NAT table, and changes the destination IP address to the private IP address of computers.

In the example above, we need to configure static NAT. To do that, the following commands are required on the router:

```
Router(config)#ip nat inside source static 192.168.1.2 100.100.100.20
Router(config)#ip nat inside source static 192.168.1.3 100.100.100.30
Router(config)#interface gigabitEthernet 0/0/0
Router(config-if)#ip nat inside
Router(config-if)#ex
Router(config)#interface gigabitEthernet 0/0/1
Router(config-if)#ip nat outside
```

After completing the configuration, we access the web page successfully.

<p align="center"><img height="200" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x2%20-%20NAT/src/web_page.png"></p>

Also, you can validate your topology `show ip nat translations` command on the router. And you can get my topology from [here.](https://github.com/wasny0ps/Network-Notes/blob/main/1x2%20-%20NAT/src/Static_NAT.pkt)

```
Router#show ip nat translations 
Pro  Inside global     Inside local       Outside local      Outside global
---  100.100.100.20    192.168.1.2        ---                ---
---  100.100.100.30    192.168.1.3        ---                ---
tcp 100.100.100.20:1025192.168.1.2:1025   100.100.100.2:80   100.100.100.2:80
```

## Dynamic NAT

In Dynamic NAT, **IP addresses are dynamically mapped to each other on a one-to-one basis as per the needs**. It establishes a **mapping between an inside local IP address and a pool of global IP addresses**. This type of translation is very useful when there are multiple users in a private network that access the Internet. These Dynamic NAT translations stay in the translation table until there is traffic flowing from the local IP address to global IP address or until the timeout time (24 hours by default) has expired.

## Dynamic NAT Configuration

> In this configuration, ACL will be used. If you don't know ACL configuration, you should [check this directory.](https://github.com/wasny0ps/Network-Notes/tree/main/1x1%20-%20Access%20Control%20Lists) 

For dynamic NAT configuration, you must do these four steps that we will do:

- Configure the interface in the inside global or local as `ip nat outside / inside` command.
- **Create a pool of global IP addresses** with `ip nat pool <pool-name> <starting-IP> <ending-IP> prefix-length <prefix-length>` command.
- **Create an access list to permit a certain network of IP addresses** with `access-list <acl-number> permit <source-ip-network> <wildcard-mask>` command.
- Lastly, **enable dynamic NAT** by using the command `ip nat inside source list <acl-number> pool <pool-name>` command.

Here is an example of dynamic NAT topology. Let's start.

  <p align="center"><img height="300" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x2%20-%20NAT/src/dynamic_NAT_topology.png"></p>

First of all, we need RIP configuration on routers. If you don't know how to configurate RIP, you should also [check this directory.](https://github.com/wasny0ps/Network-Notes/tree/main/0x8%20-%20Dynamic%20Routing)

  
```
Router(config)#int gigabitEthernet 0/0/1
Router(config-if)#ip access-group 120 out
Router(config-if)#ex
Router(config)#int gi0/0/1
Router(config-if)#ip nat outside
Router(config-if)#exit
Router(config)#int gi0/0/0
Router(config-if)#ip nat inside
Router(config-if)#exit
Router(config)#ip nat pool pool1 20.1.1.5 20.1.1.20 netmask 255.255.255.0
Router(config)#access-list 120 permit ip 192.168.1.2 0.0.0.0 10.1.1.2 0.0.0.0
Router(config)#access-list 120 permit ip 192.168.1.3 0.0.0.0 10.1.1.2 0.0.0.0
Router(config)#access-list 120 permit ip 192.168.1.2 0.0.0.0 10.1.1.3 0.0.0.0
Router(config)#access-list 120 permit ip 192.168.1.3 0.0.0.0 10.1.1.3 0.0.0.0
Router(config)#int gigabitEthernet 0/0/1
Router(config-if)#ip access-group 120 out
Router(config-if)#ex
Router(config)#ip nat inside source list 120 pool pool1 
```

## NAT Overlaod (PAT)

With Port Address Translation (PAT), a single public IP address is used for all internal private IP addresses, but a different port is assigned to each private IP address. This type of NAT is also known as NAT Overload and is the typical form of NAT used in today’s networks. It is even supported by most consumer-grade routers. PAT allows you to support many hosts with only few public IP addresses. It works by creating dynamic NAT mapping, in which a global (public) IP address and a unique port number are selected. The router keeps a NAT table entry for every unique combination of the private IP address and port, with translation to the global address and a unique port number.

## NAT Overlaod (PAT) Configuration

We will use the following example network to explain the benefits of using PAT:

|Private IP Address : Port|Public IP Address : Port| 
|:-:|:-:|
|10.0.0.2:1055|192.168.10.2:1055| 
|10.0.0.3:1055|192.168.10.2:1055|
|10.0.0.4:1055|192.168.10.2:1055|

<p align="center"><img height="300" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x2%20-%20NAT/src/PAT_topology.png"></p>

As you can see in the table, PAT uses unique source port numbers on the inside global (public) IP address to distinguish between translations. For example, if the host with the IP address of 10.0.0.3 wants to access the server on the Internet, the host’s private IP address will be translated by router to 192.168.10.1:1055 and the request will be sent to the switch. And switch will respond to 192.168.10.1:1055. Router will receive that response, look up in its NAT translation table, and forward the request to the host.

To configure PAT, the following commands are required:

- Configure the router’s inside interface using the `ip nat inside` command.
- Configure the router’s outside interface using the `ip nat outside` command.
- Configure an access list that includes a list of the inside source addresses that should be translated.
- Enable PAT with the `ip nat inside source list <acl-number> interface type overload` global configuration command.

First, we will define the outside and inside interfaces on the router:
```
Router(config)#int gigabitEthernet 0/0/0
Router(config-if)#ip nat inside
Router(config-if)#ex
Router(config)#int gigabitEthernet 0/0/1
Router(config-if)#ip nat outside
```
Next, we will define an access list that will include all private IP addresses we would like to translate:

```
Router(config)#access-list 1 permit 10.10.10.0 0.0.0.255
```

The access list defined above includes all IP addresses from the 10.10.10.0 – 10.10.10.255 range. Now we need to enable NAT and refer to the ACL created in the previous step and to the interface whose IP address will be used for translations:

```
Router(config)#ip nat inside source list 1 interface Gi0/0/1 overload
```

To verify the NAT translations, we can use the `show ip nat translations` command after hosts request a web resource from the switch. Finally, you can access our example from [here.](https://github.com/wasny0ps/Network-Notes/blob/main/1x2%20-%20NAT/src/PAT.pkt)

```
Router#show ip nat translations 
Pro  Inside global     Inside local       Outside local      Outside global
icmp 192.168.10.1:1024 10.10.10.2:2       192.168.10.2:2     192.168.10.2:1024
icmp 192.168.10.1:1    10.10.10.2:1       192.168.10.2:1     192.168.10.2:1
icmp 192.168.10.1:2    10.10.10.4:2       192.168.10.2:2     192.168.10.2:2
icmp 192.168.10.1:3    10.10.10.3:3       192.168.10.2:3     192.168.10.2:3
```

**_by wasny0ps_**

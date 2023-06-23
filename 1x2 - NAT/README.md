# NAT

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/1x2%20-%20NAT/src/NAT.gif"></p>

Since the number of IPs brought by IPv4 in the world was insufficient, an IP converter mechanism was needed. From this mechanism, users were expected to divide their IP addresses into two as local network IP and global network IP. As a result, NAT technology has entered our lives. Network Address Translation (NAT) is a service that enables private IP networks to use the internet and cloud. **NAT translates private IP addresses in an internal network to a public IP address before packets are sent to an external network**.

There is **three types of NAT soluotions** in network:
- **Static NAT**
- **Dynamic NAT**
- **PAT**

## Static NAT

Static NAT defines a one-to-one mapping from one IP subnet to another IP subnet. The mapping includes destination IP address translation **in one direction** and source IP address translation in the reverse direction. From the NAT device, the original destination address is the virtual host IP address while the mapped-to address is the real host IP address. Static NAT allows connections to be originated from either side of the network, but translation is limited to one-to-one or between blocks of addresses of the same size. For each private address, a public address must be allocated. **No address pools are necessary**.


## Dynamic NAT

In Dynamic NAT, IP addresses are dynamically mapped to each other on a one-to-one basis as per the needs. It establishes a mapping between an Inside Local IP address and a pool of Global IP addresses. This type of translation is very useful when there are multiple users in a private network that access the Internet. These Dynamic NAT Translations stay in the translation table until there is traffic flowing from the Local IP address to Global IP address or until the timeout time (24 hours by default) has expired.

## PAT

With Port Address Translation (PAT), a single public IP address is used for all internal private IP addresses, but a different port is assigned to each private IP address. This type of NAT is also known as NAT Overload and is the typical form of NAT used in today’s networks. It is even supported by most consumer-grade routers. PAT allows you to support many hosts with only few public IP addresses. It works by creating dynamic NAT mapping, in which a global (public) IP address and a unique port number are selected. The router keeps a NAT table entry for every unique combination of the private IP address and port, with translation to the global address and a unique port number.



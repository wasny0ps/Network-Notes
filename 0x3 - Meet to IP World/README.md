# Meet to IP World

## What is IP?

Shortly, **Internet Protocol** is used at **network layer** in OSI Model and we can think of it as an ID that is defined to each device surfing the internet. An IP address is a **32-bit** number that is **separated by decimals into four 8-bit groups**, called **octets**, which are separated by decimals. The numbers in each octet can **range from 0 to 255**.

## What is Subnet Mask?

Every device has an IP address with two pieces: the client or host address and the server or network address. IP addresses are either configured by a DHCP server or manually configured (static IP addresses). **The subnet mask splits the IP address into the host and network addresses, thereby defining which part of the IP address belongs to the device and which part belongs to the network**. **A subnet mask is a 32-bit number created by setting host bits to all 0s and setting network bits to all 1s**. **In this way, the subnet mask separates the IP address into the network and host addresses**. **The “255” address is always assigned to a broadcast address, and the “0” address is always assigned to a network address**. Neither can be assigned to hosts, as they are reserved for these special purposes.

## IPv4 Classes 

In the IPv4 IP address space, **there are five classes: A, B, C, D and E**. Each class has a specific range of IP addresses (and ultimately dictates the number of devices you can have on your network). Primarily, class A, B, and C are used by the majority of devices on the Internet. Class D and class E are for special uses.

|Class| Public IP Range | Private IP Range | Subnet Mask |
|:-:|:-:|:-:|:-:|
|A|1.0.0.0 - 127.255.255.255|10.0.0.0 - 10.255.255.255 | 255.0.0.0 (8 bits) |
|B|128.0.0.0 - 191.255.255.255|172.16.0.0 - 172.31.255.255|255.255.0.0 (16 bits)|
|C|192.0.0.0 - 223.255.255.255|192.168.0.0 - 192.168.255.255|255.255.255.0 (24 bits)|
|D|224.0.0.0 - 239.255.255.255|---|---|
|E|240.0.0.0 - 255.255.255.255|---|---|


## Network Address Translation - NAT

**To access the Internet, one public IP address is needed**, but we can use a private IP address in our private network. The idea of NAT is to allow multiple devices to access the Internet through a single public address. To achieve this, **the translation of a private IP address to a public IP address is required**. NAT is a process in which one or more **local IP address is translated into one or more Global IP address**. Also, it does the translation of port numbers, masks the port number of the host with another port number, in the packet that will be routed to the destination. It then makes the corresponding entries of IP address and port number in the **NAT table**. NAT generally operates on a router or firewall. 

## IPv4 vs IPv6

| IPv4 |IPv6 |
|---|---|
|Example of IPv4:  66.94.29.13|Example of IPv6: 2001:0000:3238:DFE1:0063:0000:0000:FEFB|
| IPv4 loopback (localhost) adress : **127.0.0.1** | IPv6 loopback address : **0:0:0:0:0:0:1** or **::1**|
|IPv4 has a **32-bit** address length | IPv6 has a **128-bit** address length|
| IPv4 consist of 4 fields which are separated by dot (.) | IPv6 consist of 8 fields, which are separated by colon (:)|
|It supports manual and DHCP address configuration|It supports Auto and renumbering address configuration|
|In IPv4 end to end, connection integrity is Unachievable|In IPv6 end to end, connection integrity is Achievable|
|It can generate 4.29×109 address space|Address space of IPv6 is quite large it can produce 3.4×1038 address space|
|The Security feature is dependent on application|The Security feature is dependent on application|
|Address representation of IPv4 is in decimal	| Address representation of IPv6 is in hexadecimal|
|Fragmentation performed by sender and forwarding routers	|In IPv6 fragmentation performed only by the sender|
|In IPv4 Packet flow identification is not available| In IPv6 packet flow identification are Available and uses the flow label field in the header|
|It has broadcast Message Transmission Scheme	|In IPv6 multicast and anycast message transmission scheme is available|
|In IPv4 Encryption and Authentication facility not provided	|In IPv6 Encryption and Authentication are provided |
|IPv4 can be converted to IPv6| Not all IPv6 can be converted to IPv4|
IPv4 has a header of 20-60 bytes | IPv6 has header of 40 bytes fixed |
|IPv4’s  IP addresses are divided into five different classes. Class A, B, C, D, E| IPv6 does not have any classes of IP address|
|IPv4 supports VLSM(Variable Length subnet mask) | IPv6 does not support VLSM|	

## IPv6 Abridgment

**_by wasn0ps_**

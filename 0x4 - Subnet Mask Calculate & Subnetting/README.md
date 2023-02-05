# Subnet Mask Calculate

## IP Address and Subnet Mask
A 32-bit IP address uniquely identifies a single device on an IP network. The 32 binary bits are divided into the host and network sections by the subnet mask but they are also broken into four 8-bit octets.

Because binary is challenging, we convert each octet so they are expressed in dot decimal. This results in the characteristic dotted decimal format for IP addresses—for example, 172.16.254.1. The range of values in decimal is 0 to 255 because that represents 00000000 to 11111111 in binary.

Here is an example with the IP Address  **192.168.63.8/24**. First of all, we can find out network and broadcast address. Always network address end with 0 and broadcast address end with 255 because of this **network address is 192.168.63.0** and **broadcast address is 192.168.63.255**. After that, let's find host bits. We can find the **number of host bits as 8 by subtracting the number of network bits from the total number of bits**. Later, we can calculate subnet mask of this IP address with the help of **host bit number** as shown in the pictures. 

<p align="center"><img width="400" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x4%20-%20Subnet%20Mask%20Calculate%20%26%20Subnetting/source/ip_addressing.png"></p> 

<p align="center"><img width="400" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x4%20-%20Subnet%20Mask%20Calculate%20%26%20Subnetting/source/subnetmask-calculate.png"></p> 


Here some more examples table about ip addressing.

|Example IP|Host Bit|Network Adress|Broadcast Address|Subnet Mask|
|:---:|:---:|:---:|:---:|:---:|
|144.128.16.9/24|8|144.128.16.0|144.128.16.255|255.255.255.0|
|172.127.46.10/22|10|172.127.44.0|172.127.47.255|255.255.252.0|
|192.168.36.7/26|6|192.168.36.0|192.168.36.63|255.255.255.192|
|27.129.10.2/30|2|27.129.10.0|27.129.10.3|255.255.255.252|
|56.81.33.17/16|16|56.81.0.0|56.81.255.255|255.255.0.0|
|14.34.64.4/23|9|14.34.64.0|14.34.65.255 | 255.255.254.0|
|20.20.20.20/13|19|20.16.0.0|20.23.255.255 | 255.248.0.0|
|39.70.2.1/18|14|39.70.0.0 |39.70.63.255  | 255.255.192.0|
|100.100.100.100/8|24|100.0.0.0|100.255.255.255 |255.0.0.0|
|205.21.53.13/3|29|192.0.0.0|223.255.255.255 |224.0.0.0|
|114.182.47.31/9|23|114.128.0.0|114.255.255.255  |255.128.0.0|


# Subnetting

The process of dividing a network into 2/more networks is called subnetting. A subnet, or subnetwork, is a network **inside a network**. **Subnets make networks more efficient**. Through subnetting, network traffic can travel a shorter distance without passing through unnecessary routers to reach its destination. Also, we can **always create 2^n subnets in a network**. For example if we wanted to dividing 192.168.10.0/24 network into 3 subnetworks, we wouldn't. Instead, we can dividing 192.168.10.0/24 network into 4 subnetworks and use three of them. Time to understand how subnetting works.

## How Divide Subnetting?

Subnetting works are smiliar to ip addressing process. Again, we convert the IP address into binary format to find the subnet mask and network address. However, there is an important point which means our network ID is current network ID + intended numbers of subnet. Please, keep an eye out! 

Afterwards, we draw a perpendicular line to divide it into the subnet immediately after the network ID. It is where the magic happens. After the last dot, we need to increment like 1,10,11,100,101,110 the remainder starting from 0. Let's look at example pictures for better understanding.

<p align="left"><img width="500" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x4%20-%20Subnet%20Mask%20Calculate%20%26%20Subnetting/source/subnet.png"></p> 

<p align="center"><img  src="https://github.com/wasny0ps/Network-Notes/blob/main/0x4%20-%20Subnet%20Mask%20Calculate%20%26%20Subnetting/source/subnetting.png"></p> 

If we take the example in the picture as reference, we have **4 subnets**. There are : 

|Subnet|Network Address| Broadcast Address|Avaliable IP Range|
|:-:|:-:|:-:|:-:|
|A|192.168.10.0|192.168.10.63|192.168.10.1-62|
|B|192.168.10.64|192.168.10.127|192.168.10.65-126|
|C|192.168.10.128|192.168.10.191|192.168.10.129-190|
|D|192.168.10.192|192.168.10.255|192.168.10.193-254|

# Subnetting With Serial Connection

The Serial Connection is used to create a WAN connection with the help of a service provider who offers a dedicated leased line to its customers.
Business organizations buy leased lines to establish a WAN connection to connect with different offices and business sites that could physically be thousands of miles apart. Businesses have to pay for these leased lines according to the service availed. And accordingly, the service providers charge for this service i.e. based on the bandwidth they offer to their client organizations.

One of the connections used for a leased line is the Serial Connection in Cisco based networks. If we have Cisco routers on both sides of the network then the default encapsulation known as HDLC will be used by the Cisco routers. However, this will not work with other brands routers (i.e. with the non-Cisco routers) because this protocol is solely a Cisco proprietary.
If we want to establish successful connection with router of other vendor then we must configure the same data link protocol on both router. If there will be a mismatch then connection cannot be established and we will see the status of the interface as down under data link.

If we are configuring new cisco router then by default the data link protocol would be HDLC however if we are configuring old device then we should check the configuration and if there is a mismatch then we have to configure the same protocol on both routers.

In this example, we will configure a Serial Connection between the routers. We will set up a clock rate at 56000, which will provide the speed of 56 Kbps. In a real world, the DCE side of the cable is configured by the service provider. Generally, the clock speed is configured according to the availability of the bandwidth speed that the service provider is offering. The following example uses a serial cable that will simulate a service provider. We will configure the clock speed on the router that has DCE side connected.

## Default Configration

In the first step, we must subnetting network in the topology and assign IP address correctly. In my example topology, I divided 192.168.10.0/24 network into 4 subnetworks. After that, I configured routers and switches. In what fallows, I connected four routers with serial cable. If you dont't know how to configure, you can learn from [here](https://github.com/wasny0ps/Network-Notes/tree/main/0x5%20-%20Router%20%26%20Switch%20Configration).

To use serial connection, you must use serial cable with **NIM-2T** module in router. When you turn off your router you can add this module to physical port as shown in example picture.

<p align="center"><img width="500" height="400" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x4%20-%20Subnet%20Mask%20Calculate%20%26%20Subnetting/source/serial.png"></p> 

Later on, you can cord serial cable to serail port of the router. Before serial interface configuration, my example topology looks like:

<p align="center"><img  src="https://github.com/wasny0ps/Network-Notes/blob/main/0x4%20-%20Subnet%20Mask%20Calculate%20%26%20Subnetting/source/subnetted_topology.png"></p> 


## Serial Interface Configuration

**_by wasny0ps_**


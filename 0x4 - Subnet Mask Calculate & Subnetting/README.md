# Subnet Mask Calculate

## IP Addressing
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

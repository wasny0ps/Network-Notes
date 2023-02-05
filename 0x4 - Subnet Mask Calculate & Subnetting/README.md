# Subnet Mask Calculate

## IP And Subnet Mask
A 32-bit IP address uniquely identifies a single device on an IP network. The 32 binary bits are divided into the host and network sections by the subnet mask but they are also broken into four 8-bit octets.

Because binary is challenging, we convert each octet so they are expressed in dot decimal. This results in the characteristic dotted decimal format for IP addresses—for example, 172.16.254.1. The range of values in decimal is 0 to 255 because that represents 00000000 to 11111111 in binary.

Here is an example with the IP Address  **192.168.63.8/24**. First of all, we can find out network and broadcast address. Always network address end with 0 and broadcast address end with 255 because of this **network address is 192.168.63.0** and **broadcast address is 192.168.63.255**. After that, let's find host bits. We can find the **number of host bits as 8 by subtracting the number of network bits from the total number of bits**. Later, we can calculate subnet mask of this IP address with the help of **host bit number**. 

<p align="center"><img width="400" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x4%20-%20Subnet%20Mask%20Calculate%20%26%20Subnetting/source/ip_addressing.png"></p> 

<p align="center"><img width="400" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x4%20-%20Subnet%20Mask%20Calculate%20%26%20Subnetting/source/subnetmask_calculate.png"></p> 




# Subnet Mask Calculate

## What is IP?

Shortly, **Internet Protocol** is used at **network layer** in OSI Model and we can think of it as an ID that is defined to each device surfing the internet. An IP address is a **32-bit** number that is **separated by decimals into four 8-bit groups**, called **octets**, which are separated by decimals. The numbers in each octet can **range from 0 to 255**.

Throughout this article, I will be using the following network address as our example:

**IP Adress : 195.192.32.0**

This address will serve as our original network identifier (network ID); it is the IP address that identifies the larger network that we will be working with. 

## What is Subnet Mask?

An IP address alone does not provide all of the information necessary to begin subnetting (dividing a network into smaller subnetworks, or **subnets**). This is where the **subnet mask** comes in. A subnet mask, like an IP address, is a **32-bit number separated into four octets**. The purpose of the subnet mask is to differentiate the portion of an IP address that is used to identify the network from the portion used to identify the hosts.

# VPN

<p align="center"><img height="300" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x5%20-%20VPN%20%26%20IPSec/src/VPN.png"></p>

VPN stands for the virtual private network. A virtual private network (VPN) is a technology that creates a **safe and encrypted connection over a less secure network**, such as the internet. A Virtual Private Network is a way to extend a private network using a public network such as the internet. The name only suggests that it is a Virtual “private network” user can be part of a local network sitting at a remote location. It makes use of tunneling protocols to establish a secure connection. 

|Advantages of VPN|Desadvantages of VPN|
|-|-|
|Remote access to private networks|Slowe connection speed|
|Security and privacy|Higher CPU load|
|Access to geo-blocked resources|Possible activity logging and traffic inspection|
|No additional hardware needed|Suboptimal or unwanted routing|


## Types of VPNs

There are many different types of VPNs, but you should definitely be familiar with the three main types:

- **SSL VPN**
- **Site-to-site VPN**
- **Client-to-Server VPN**

### SSL VPN

<p align="center"><img height="275" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x5%20-%20VPN%20%26%20IPSec/src/SSL_VPN.png"></p>

Often not all employees of a company have access to a company laptop they can use to work from home. During the corona crisis in Spring 2020, many companies faced the problem of not having enough equipment for their employees. In such cases, use of a private device (PC, laptop, tablet, mobile phone) is often resorted to. In this case, companies fall back on an SSL-VPN solution, which is usually **implemented via a corresponding hardware box**.

The prerequisite is usually an HTML-5-capable browser, which is used to call up the company's login page. HTML-5 capable browsers are available for virtually any operating system. Access is guarded with a username and password.

### Site to Site VPN

<p align="center"><img height="275" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x5%20-%20VPN%20%26%20IPSec/src/Site_to_Site_VPN.png"></p>

A site-to-site VPN is essentially a private network designed to hide private intranets and allow users of these secure networks to access each other's resources. **A site-to-site VPN is useful if you have multiple locations in your company, each with its own local area network connected to the WAN**. Site-to-site VPNs are also useful if you have two separate intranets between which you want to send files without users from one intranet explicitly accessing the other.

**Site-to-site VPNs are mainly used in large companies**. They are complex to implement and **do not offer the same flexibility as SSL VPNs**. However, they are **the most effective way to ensure communication within and between large departments**.

### Client to Server VPN

Connecting via a VPN client can be imagined as if you were **connecting your home PC to the company with an extension cable**. Employees can dial into the company network from their home office via the secure connection and act as if they were sitting in the office. However, a **VPN client must first be installed and configured on the computer**. This involves the user not being connected to the internet via his own ISP, but establishing a direct connection through his/her VPN provider. This essentially shortens the tunnel phase of the VPN journey. Instead of using the VPN to **create an encryption tunnel to disguise the existing internet connection, the VPN can automatically encrypt the data before it is made available to the user**.

**This is an increasingly common form of VPN**, which is particularly useful for providers of insecure public WLAN. It **prevents third parties from accessing and compromising the network connectio**n and **encrypts data all the way to the provider**. It also **prevents ISPs from accessing data that, for whatever reason, remains unencrypted and bypasses any restrictions on the user's internet access**.

**The advantage of this type of VPN access is greater efficiency and universal access to company resources**. Provided an appropriate telephone system is available, the employee can, for example, connect to the system with a headset and act as if he/she were at their company workplace. For example, customers of the company cannot even tell whether the employee is at work in the company or in their home office.

## Concept of A Tunnel

VPNs differ in their architecture and transport protocols used to establish the overlay network. The VPN architecture may be either point-to-point or site-to-site. A point-to-point VPN is used to provide a device with remote access to a private network. In contrast, a site-to-site VPN is used to establish an **imaginary bridge between two private networks as if they were connected directly**:

<p align="center"><img height="300" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x5%20-%20VPN%20%26%20IPSec/src/VPN_architecture.png"></p>

The transport connection established between two VPN entities is usually called a tunnel and the process of routing traffic through that tunnel is called **tunneling**. This happens only by using software without requiring any additional hardware. Of course, there exist also hardware VPN boxes, but they are usually used for purposes requiring very strong security measures.

According to the ISO/OSI layered model, the tunnel can be theoretically established above any level starting from the Data link layer (L2) and going over the Network Layer (L3) to higher layers. Moreover, the overlay network can be either an L2 or L3 network. In the case of L2, we’re talking about bridging (or switching), whereas in the case of L3 about routing. To give an example, a VPN may provide an L2 service over the TCP transport layer.

## VPN Protocols

VPN protocols are usually designed for a particular combination of the overlay network layer and the transport layer. The most common VPN protocols are:

- **PPTP (Point-to-Point Tunneling Protocol):** provides a point-to-point L2 service (PPP) over TCP (Transport layer). This protocol was once very popular but is now obsolete.
- **PPPoE (Point-to-Point over Ethernet):** provides a point-to-point L2 service (PPP) over Ethernet (L2).
- **L2TP (Layer 2 Tunneling Protocol):** provides a point-to-point L2 service (PPP) over UDP (Transport layer).
- **IPsec (Internet Protocol Security):** provides both point-to-point and site-to-site L3 service over IPv4 and v6 (L3) depending on the operation mode.
- **SSL & TLS:** Both provide a point-to-point L3 service over a secure transport connection established by using either the SSL or TLS protocol.
- **SSTP (Secure Socket Tunneling Protocol):** provides a point-to-point L2 service (PPP) over SSL or TLS secure connection. It was designed to replace less secure PPTP and L2TP.
- **DTLS (Datagram Transport Layer Security):** provides a point-to-point L3 service over UDP (Transport layer).
- **OpenVPN:** It is an open-source VPN that can provide both a point-to-point and site-to-site L3 service over a secure transport connection (L4) established by using either the SSL or TLS protocol.
- **SSH Tunnels:** They are used for tunneling connections using SSH. They are also a kind of VPN, but provide an L4 service, so it’s rather called port forwarding. We mention SSH tunnels because they provide a transport service over an SSH connection and don’t need any special software (VPN server or client) to be installed on both sides of the tunnel. For more information and usage examples see the article on SSH tunneling and proxying.

## Privacy of VPN

Although a **VPN provides security by encrypting the transmitted data, it doesn’t ensure privacy**. The remote VPN server may be logging usernames, IP addresses, and user activities. Moreover, some services may use IP address-based geolocation or a Wi-Fi positioning system to reveal the user’s location, sometimes with surprising precision. When using a VPN server, the location service reveals only the location of the VPN server, but not the location of the client. So what can we do if we don’t want to reveal our identity or location to a VPN server or a remote service? We can establish a VPN tunnel to another VPN server (hop) inside a VPN tunnel. We can even repeat it several times by nesting VPN tunnels. This nesting method is called **multi-hop VPN** or **onion routing**. At each subsequent hop, a nested VPN layer is dropped, much like peeling away layers of an onion:

<p align="center"><img width="700" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x5%20-%20VPN%20%26%20IPSec/src/onion_routing.png"></p>

This approach is used by the well-known Tor relay network. Because the VPN client reaches the target (the innermost tunnel endpoint) indirectly over multiple hops, it is very hard to reveal the client’s real IP address and identity. Of course, this is all achieved at the burden of higher overhead and slower virtual connection speed.



## IPsec

<p align="center"><img width="600" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x5%20-%20VPN%20%26%20IPSec/src/ipsec.png"></p>

IPSec is a security protocol developed by the IETF (Internet Engineering Task Force) to **meet the security needs of IP protocols using encryption and security services**. Thanks to this protocol, the data reaches the destinations that need to go safely on the network. **It works at the IPSec network layer, providing protection and authentication of IP packets between IPSec devices**. Since IPSec works at the network layer, **it encrypts every data independently of the application and enables the data to travel easily on the Internet with the header it creates after the password--. Therefore, it forms the infrastructure of VPN (Virtual Private Network) technology today. The terms IPsec and VPN are often confused with each other. **VPN is used to establish a virtual network between two endpoints**. **IPSec provides security-enhancing functions to the VPN connections created**. There are different ways to create a VPN at layer 2 and layer 3. IPSec is just one of these ways. Today, with the development of the Internet, these two concepts are intertwined as IPSec VPN connections can be made easily.

Since IPSec protocols work at the network layer, they are **more flexible than other security protocols**. SSL (Secure Socket Layer - Secure Socket Layer), TLS (Transport Layer Security - Transit Layer Security), SSH (Secure Shell - Secure Shell) 4 and higher layers work. **IPSec can protect layer 4 and higher layer protocols, including TCP and UDP**. One advantage of **IPSec over other security protocols is that IPSec can work independently of the application layer, that is, the software of the users**. However, in order to use other protocols (such as SSL), the user's software must support that protocol.

The IPSec framework includes 5 basic building blocks:

<p align="center"><img height="350" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x5%20-%20VPN%20%26%20IPSec/src/IPsec_framework.png"></p>

**IPSec can provide secure data transfer between gateways, between clients, and between gateways and clients. Using the IPSec framework, 4 basic security requirements can be realized.**

### Confidentiality

It ensures confidentiality using IPSec encryption methods. The degree of security depends on the length of the key used in the encryption algorithm. The shorter the key, the easier it is to crack the password and the vulnerability occurs. For example, it may take approximately 1 year for a 64-bit key to be cracked by the computer.

- **Des:** It is a system that uses a 56-bit symmetric encryption technique. If the data encrypted with the same key can be opened with the same key, it means that a symmetric encryption algorithm is used.
- **3Des:** It is a variant of Des. It offers stronger security than Des by using 3 independent 56-bit encryptions.
- **AES:** It is a more secure system than 3Des and Des. It can have three different key lengths, 128 bits, 192 bits and 256 bits.
- **Seal:** It is a system developed by Phillip Rogaway and Don Coppersmith in 1993, using a 160-bit key length.

### Integrity

By using IPSec data integrity algorithms, it ensures that the data to be transmitted reaches the destination without any change. **HMAC (Hashed Message Authentication Codes - Encrypted Message Authentication Code) is an algorithm that protects the integrity of the data with the help of its "hash" value**. Its purpose is not to ensure that the data is encrypted, but to ensure that the data is correct by preventing the data from being changed on the way. On the sender side, the data is encrypted and a Hash value is generated by passing it through the Hash algorithm. On the receiver side, it is checked whether the Hash value produced by reversing the Hash algorithm is the same as the value obtained on the sender side. If the value is the same, the integrity of the data is ensured, if it is different, the data has been changed and is not used. There are two types of HMAC algorithms:

- **HMAC – MD5:** It uses 128-bit encrypted data. The output from the algorithm is again a 128-bit Hash value.
- **HMAC – SHA1:** It uses a 160-bit long keying technique. This algorithm is stronger than HMAC – MD5 in terms of security.


### Authentication

In general, the authentication of a document is by signing. In electronic devices, on the other hand, authentication is provided with the help of packages containing the special password of the sending device, called digital signature. IPSec uses two different algorithms to provide authentication, PSK and RSA.

- **PSK:** **It stands for pre-shared secret keying method**. A numerical value determined to provide authentication on devices is **manually entered into the required devices**. After each device learns the value of the device opposite, the network becomes secure and data transfer begins. The entered numeric value is accepted as the signature of the device and authentication is provided.
- **RSA:** **It is an asymmetric encryption algorithm**. Instead of using a single key as in symmetric ciphers, it uses two keys, one private and the other public. This is especially true for systems with multiple users. **The most important factor affecting the reliability and speed of the system is the length of the key used**.

Another method to ensure authentication is the protocol called **IKE (Internet Key Exchange)**. **IKE performs authentication through various methods such as username and password, one-time password, and digital certificates**.

### Secure Key Exchange

**IPSec uses algorithms called Diffie-Helman to exchange public keys between devices**. The easiest method to perform encryption and decryption between devices is to exchange keys. Thanks to Diffie-Helman, briefly DH algorithms, key exchange between devices can be performed seamlessly even when transferring data over an unsecured channel.


## IPSec Protocols

As shown in the figure before, IPSec protocols are ranked 1st in the IPSec building block. There are 2 types, AH and ESP.

### AH (Authentication Header)

The AH protocol is generally used when privacy is not required or allowed. In order to prevent changes that may occur during transmission and to protect the integrity of the sent packet, the IP packet is given a sequence number. **If the packages reach the recipient side in a way that does not match the sequence number, the packages are not accepted**. However, since **AH does not provide privacy, it can create a security vulnerability if used alone**.

### ESP (Encapsulating Security Payload)

The ESP protocol can provide both **privacy and authentication**. This protocol primarily **encrypts IP packets with sequence numbers given by AH using specified algorithms** and decrypts them using the same algorithms when they reach the destination. Thus, the vulnerability that may occur by AH is prevented.

AH and ESP protocols can be applied to IP packets in two different ways.

#### Transport Mode

In this mode, security is a feature provided only at the Transport layer and above from the OSI layers. Transport mode provides protection of IP packet with AH or ESP. While protection takes place over the payload portion of the packet, the actual IP address does not change. It can be used by devices within the same local network.

#### Tunnel Mode

In this mode, security is performed over the entire IP packet. The real IP packet is encrypted and encapsulated with the help of another IP packet. Generally, tunnel mode is used when data is going to traverse a different network. In tunnel mode, encryption is done on the gateway while data leaves the network. There is no need to use IPSec in internal networks.


**_by wasny0ps_**

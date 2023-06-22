# Firewall
<p align="center"><img height="300" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x3%20-%20Network%20Security%20Devices/src/firewall.gif" /></p>

A firewall is a network security device that **monitors incoming and outgoing network traffic** and **decides whether to allow or block specific traffic based on a defined set of security rules**. Firewalls have been a first line of defense in network security for over 25 years. They establish a barrier between secured and controlled internal networks that can be trusted and untrusted outside networks, such as the Internet. **A firewall can be hardware, software, software-as-a service (SaaS), public cloud, or private cloud (virtual)**. Also, it is divided into two groups according to the firewall structure.

## Software Firewall

A software firewall is a special type of computer software that runs on a computer/server. Its main purpose is to protect your computer/server from outside attempts to control or gain access and depending on your choice of a software firewall. A software firewall can also be configured for checking any suspicious outgoing requests.

### Advantages Of Software Firewall
- Helpful in blocking particular sites.
- Juniors and parental controls can be supervised.
- Ease in maintenance.
- Valuable for home users.
- Assignment of different levels of access and permissions to the user can be done with ease.

### Disadvantages Of Software Firewall
- Installation and up-gradation are required on individual computers.
- Slow performance of the system.
- Due to its installation, system resources are consumed.
- Does not work on smart TVs, gaming consoles, etc.

## Hardware Firewall
It is physical piece of equipment planned to perform firewall duties. A hardware firewall can be a computer or a dedicated piece of equipment which serve as a firewall. Hardware firewall are incorporated into the router that is situated between the computer and the internet gateway. 

### Advantages Of Hardware Firewall
- Independently run so less prone to cyber-attacks.
- Installation is external so resources are free from the server.
- Increased bandwidth enables the handling of more data packets per second.
- Reduced latency.
- VPN connection is also supported for increased security and encryption.

### Disadvantages Of Hardware Firewall
- Hardware devices can take extra space.
- A skilled IT person is required.
- Upgradation challenge as it is not cost-effective because multiple devices need to be replaced.

## Software Firewall vs Hardware Firewall	

|Parameter|Software Firewall|Hardware Firewall|
|:-:|-|-|
|Configuration|Configuration of a software firewall is easy.|Configuration of hardware firewall is not easy.|
|Operates on|A software Firewall operates on the system.|Hardware Firewall do not operate on the system.|
|Working|It is installed on individual devices like computes and phones which results in blocking users or devices from accessing the individual components of the network.|It is required to install the device between the computer and the Internet so that it will not be easily accessible. The installation requires a connection of network cable with the firewall rather than directly connecting to the router.|
|Cost|It is less expensive to install though the cost may increase in case of variation in computers.|It is more expensive than a software firewall as an initial investment is required based on the protection level.|
|Flexibility|It is flexible, you can choose which application has to be installed.|It is not flexible like software firewall.|
|Installation|It is installed inside the individual system.|It is installed outside the system.|
|Protects|It protects one system at a time and is not enabled for smart TVs, gaming consoles, and other devices.|It protects a whole network at a time.|
|Performance|It makes the performance of computers slows down.|It doesn’t affect the performance of the computer.|
|Requirement|It is needed to be installed on every individual system on a network.|It needs only one hardware to be installed for a whole network.|
|Blocking|In software firewall, content based on keywords can be blocked.|A domain or website can be blocked using hardware firewall.|


# WAF

<p align="center"><img height="300" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x3%20-%20Network%20Security%20Devices/src/WAF.gif" /></p>

A web application firewall, or WAF, is a security tool for **monitoring, filtering and blocking incoming and outgoing data packets from a web application or website**. WAFs can be **host-based**, **network-based** or **cloud-based** and are typically **deployed through reverse proxies and placed in front of an application or website**. WAFs can run as network appliances, server plugins or cloud services, inspecting each packet and **analyzing application layer (Layer 7) logic according to rules to filter out suspicious or dangerous traffic**.

- **Network-based WAF:** It is generally hardware-based. Since they are installed locally they minimize latency, but network-based WAFs are the **most expensive option** and also **require the storage and maintenance of physical equipment**.
- **Host-based WAF:** It may be fully integrated into an application’s software. This solution is less expensive than a network-based WAF and offers more customizability. The downside of a host-based WAF is the consumption of local server resources, implementation complexity, and maintenance costs. These components typically require engineering time, and may be costly.
- **Cloud-based WAF:** It offers an affordable option that is very easy to implement; they usually offer a turnkey installation that is as simple as a change in DNS to redirect traffic. Cloud-based WAFs also have a **minimal upfront cost**, as users pay monthly or annually for security as a service. Cloud-based WAFs can also offer a solution that is **consistently updated to protect against the newest threats without any additional work** or cost on the user’s end.

# Honeypot

<p align="center"><img height="350" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x3%20-%20Network%20Security%20Devices/src/honeypot.png" /></p>

A honeynet is a network of honeypots that is **designed to look like a real network**, complete with multiple systems, databases, servers, routers and other digital assets. Since the honeynet, or honeypot system, mimics the sprawling nature of a typical network, it tends to engage cybercriminals for a longer period of time. Given the size of the honeynet, it is also possible to manipulate the environment, luring adversaries deeper into the system in order to gather more intelligence about their capabilities or their identities.

# Unified Threat Management (UTM)

<p align="center"><img height="350" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x3%20-%20Network%20Security%20Devices/src/UTM.png" /></p>

UTM refers to when multiple security features or services are combined into a single device within your network. Using UTM, your network’s users are protected with several different features, including antivirus, content filtering, email and web filtering, anti-spam, and more. UTM enables an organization to consolidate their IT security services into one device, potentially simplifying the protection of the network. As a result, your business can monitor all threats and security-related activity through a single pane of glass. In this way, you attain complete, simplified visibility into all elements of your security or wireless architecture.

## Data Loss Prevention (DLP)

The data loss prevention you **get with a UTM appliance enables you to detect data breaches and exfiltration attempts and then prevent them**. To do this, the data loss prevention system **monitors sensitive data**, and when it identifies an attempt by a malicious actor to steal it, blocks the attempt, **thereby protecting the data**.


# Intrusion Detection System (IDS)

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/1x3%20-%20Network%20Security%20Devices/src/IDS.png" /></p>

IDS observes network traffic for malicious transactions and sends immediate alerts when it is observed. It is software that **checks a network or system for malicious activities or policy violations**. **Each illegal activity or violation is often recorded either centrally using a SIEM system or notified to an administration**. IDS monitors a network or system for malicious activity and protects a computer network from unauthorized access from users, including perhaps insiders. The intrusion detector learning task is to build a predictive model capable of distinguishing between **‘bad connections’ (intrusion/attacks)** and **‘good’ normal connections**.

- Usually, ***IDS connects to switch*** with **SPAN port**.

***IDS have two types detection method***:

- **Signature-based Method:** Signature-based IDS detects the attacks on the basis of the specific patterns such as the number of bytes or a number of 1s or the number of 0s in the network traffic. It also detects on the basis of the already known malicious instruction sequence that is used by the malware. The detected patterns in the IDS are known as signatures. Signature-based IDS can easily detect the attacks whose pattern (signature) already exists in the system but it is quite difficult to detect new malware attacks as their pattern (signature) is not known.
- **Anomaly-based Method:** Anomaly-based IDS was introduced to detect unknown malware attacks as new malware is developed rapidly. In anomaly-based IDS there is the use of machine learning to create a trustful activity model and anything coming is compared with that model and it is declared suspicious if it is not found in the model. The machine learning-based method has a better-generalized property in comparison to signature-based IDS as these models can be trained according to the applications and hardware configurations.

## How Does An IDS work?

- An IDS (Intrusion Detection System) monitors the traffic on a computer network to detect any suspicious activity.
- It analyzes the data flowing through the network to look for patterns and signs of abnormal behavior.
- The IDS compares the network activity to a set of predefined rules and patterns to identify any activity that might indicate an attack or intrusion.
- If the IDS detects something that matches one of these rules or patterns, it sends an alert to the system administrator.
- The system administrator can then investigate the alert and take action to prevent any damage or further intrusion.


## Advantages Of IDS
- **Detects malicious activity:** IDS can detect any suspicious activities and alert the system administrator before any significant damage is done.
- **Improves network performance:** IDS can identify any performance issues on the network, which can be addressed to improve network performance.
- **Compliance requirements:** IDS can help in meeting compliance requirements by monitoring network activity and generating reports.
- **Provides insights:** IDS generates valuable insights into network traffic, which can be used to identify any weaknesses and improve network security.

## Desadvantages Of IDS
- **It doesn't block an attack. Just detect it.**
- **It doesn't make provision for attacks so network administrator should make it.**

# Intrusion Prevent System (IPS)

<p align="center"><img width="500" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x3%20-%20Network%20Security%20Devices/src/IPS.png" /></p>


It is a network security application that **monitors network or system activities for malicious activity**. Major functions of intrusion **prevention systems are to identify malicious activity**, **collect information about this activity**, **report it and attempt to block or stop it**. IPS typically record information related to observed events, notify security administrators of important observed events and produce reports. Many IPS can also respond to a detected threat by attempting to prevent it from succeeding. They use various response techniques, which involve the IPS stopping the attack itself, changing the security environment or changing the attack’s content.

- ***IPS connects to firewall for checking packets before come to the switches***. Thus, **it checks every packet including with packet's content**.

Also there three types of detection method IPS used:

- **Signature-based detection:** Signature-based IDS operates packets in the network and compares with pre-built and preordained attack patterns **known as signatures**.
- **Statistical anomaly-based detection:** Anomaly based IDS monitors network traffic and **compares it against an established baseline**. **The baseline will identify what is normal for that network and what protocols are used**. However, It may raise a false alarm if the baselines are not intelligently configured.
- **Stateful protocol analysis detection:** This IDS method recognizes divergence of protocols stated by comparing observed events with **pre-built profiles of generally accepted definitions of not harmful activity**. 


## Types Of ISP

- **Network-Based IPS:** It is installed at the **network perimeter** and monitors all **traffic that enters and exits the network**.
- **Host-Based IPS:** It is installed on **individual hosts** and monitors the **traffic that goes in and out of that host**.

## Advantages Of IPS

- **Protection Against Known and Unknown Threats:** An IPS can block known threats and also detect and block unknown threats that haven’t been seen before.
- **Real-Time Protection:** An IPS can detect and block malicious traffic in real-time, preventing attacks from doing any damage.
- **Compliance Requirements:** Many industries have regulations that require the use of an IPS to protect sensitive information and prevent data breaches.
- **Cost-Effective:** An IPS is a cost-effective way to protect your network compared to the cost of dealing with the aftermath of a security breach.
- **Increased Network Visibility:** An IPS provides increased network visibility, allowing you to see what’s happening on your network and identify potential security risks.

## Desadvantages Of IPS

- **Delays network traffic**.
- **If IPS's sensor is overflow, it will effect the network traffic**.

## IPS vs IDS

- Intrusion prevention systems are placed in-line and are able to actively prevent or block intrusions that are detected.
- IPS can take such actions as sending an alarm, dropping detected malicious packets, resetting a connection or blocking traffic from the offending IP address.
- IPS also can correct cyclic redundancy check (CRC) errors, defragment packet streams, mitigate TCP sequencing issues and clean up unwanted transport and network layer options. 

**_by wasny0ps_**

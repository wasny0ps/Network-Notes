# Contents
- [**Firewall**](https://github.com/wasny0ps/Network-Notes/tree/main/1x3%20-%20Network%20Security%20Devices#firewall)
- [**WAF**](https://github.com/wasny0ps/Network-Notes/tree/main/1x3%20-%20Network%20Security%20Devices#waf)
- [**Honeypot**](https://github.com/wasny0ps/Network-Notes/tree/main/1x3%20-%20Network%20Security%20Devices#honeypat)
- [**UTM**](https://github.com/wasny0ps/Network-Notes/tree/main/1x3%20-%20Network%20Security%20Devices#utm)
- [**NGFW**](https://github.com/wasny0ps/Network-Notes/tree/main/1x3%20-%20Network%20Security%20Devices#ngfw)
- [**IDS**](https://github.com/wasny0ps/Network-Notes/tree/main/1x3%20-%20Network%20Security%20Devices#intrusion-detection-system-ids)
- [**IPS**](https://github.com/wasny0ps/Network-Notes/tree/main/1x3%20-%20Network%20Security%20Devices#intrusion-prevent-system-ips)

# Firewall

# WAF

# Honeypot

# UTM

# NGFW

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

# Contents
- [**Firewall**]()
- [**WAF**]()
- [**Honeypat**]()
- [**UTM**]()
- [**NGFW**]()
- [**IDS**](https://github.com/wasny0ps/Network-Notes/edit/main/1x3%20-%20Network%20Security%20Devices/README.md#intrusion-detection-system-ids)
- [**IPS**]()
# Intrusion Detection System (IDS)

<p align="center"><img src="https://github.com/wasny0ps/Network-Notes/blob/main/1x3%20-%20Network%20Security%20Devices/src/IDS.png" /></p>

IDS observes network traffic for malicious transactions and sends immediate alerts when it is observed. It is software that **checks a network or system for malicious activities or policy violations**. **Each illegal activity or violation is often recorded either centrally using a SIEM system or notified to an administration**. IDS monitors a network or system for malicious activity and protects a computer network from unauthorized access from users, including perhaps insiders. The intrusion detector learning task is to build a predictive model capable of distinguishing between **‘bad connections’ (intrusion/attacks)** and **‘good’ normal connections**.

- Usually, ***IDS connects to switch*** with **SPAN port**.

## How Does IDS work?

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

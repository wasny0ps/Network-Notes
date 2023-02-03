# Router Components

A wireless router connects directly to a modem by a cable then a router can receive and transmit information or data to the internet. Then the router starts to communicate with the wifi network and provides internet access to all devices within the network range of the router.

A generic router consists of the following components: 

- **Input Port** : This is the interface by which packets are admitted into the router, it performs several key functions as terminating the physical link at the router.

* **Switching Fabric** : This is the main component of the Router, it connects the input ports with the output ports. It is kind of a network inside a networking device.

+ **Output Ports** : This is the segment from which packets are transmitted out of the router. The output port looks at its queuing buffers and takes packets.

- **Routing Processor** : It executes the routing protocols, and works like a traditional CPU.


Here some router components important to know : 

**CPU** :  Executes operating system instructions.

**RAM** : Random Access Memory, this is similar to the RAM used on your desktop computers. It is volatile in nature which means that it loses the stored information if it is restarted or powered down.
The running configuration of the router is stored or held in the RAM. RAM is very fast in nature thus the running configuration is held in it.
Any changes that are done in the configuration are stored in the RAM till it is saved to the NVRAM.

**NVRAM** : Non-volatile Random Access Memory:  the start-up configuration is stored in this memory component. When a router is booted the IOS (Internetwork Operating System) reads this memory and gets the configuration file.
This memory can be erased if required. The router’s running configuration can be copied to the NVRAM and this can retain the configuration even if the router was shut down or power down, thus avoiding reconfiguration of the router every time it is powered off.

**ROM** : This is the Read Only Memory which is available on the motherboard of the Cisco router. This contains the initial Bootstrap program and also the POST (Power on Self-Test) instructions. These ROM components or chips can be upgraded or replaced if required. Also it isn't changeable, only readable.

**Bootstrap** : It is a software that helps router to start working.

**POST** : Post stands for the power on self test. When the router power on router test itself and find that how many modules on me and how many interfaces exist on me. Basically POST is the self test of the router for the checking of the hardware.

**ROM Monitor** : Low level debugging in router.

**FLASH** : Flash is the storage where the IOS of the router stores.

**FLASH RAM** : This is the Read Only Memory which is available on the motherboard of the Cisco router. This contains the initial Bootstrap program and also the POST (Power on Self-Test) instructions. These ROM components or chips can be upgraded or replaced if required. Different version of IOS can be stored on a Flash memory. This memory can retain the configuration in even of a restart or power down. This memory stores the IOS in a compressed form.

**Mini OS** : When the router's operating system is down, mini os helps to work system until error fixed.

**_by wasny0ps_**

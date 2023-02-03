# Network Configration

## Router Configration

After creating a topology, the first thing you need to do is to give ip and subnet mask to the legs of the router in the network. Then you can do other configration in router CLI. However, before configrate the router, we should look at **CLI modes**. 

- **User Execution Mode** : As soon as the interface up message appears and press enter, the router> prompt will pop up. This is called user execution mode. This mode is limited to some monitoring commands. 

- **Privileged Mode** : As we type enable to user mode, we enter into Privileged mode where we can view and change the configuration of the router. Different commands like show running-configuration, show IP interface brief, etc can run on this mode which is used for troubleshooting purposes.

- **Global Configuration Mode** : As we type configure terminal to the user mode, we will enter into the global configuration mode. Commands entered in these modes are called global commands and they affect the running configuration of the router. In this mode, a different configuration like making a local database on the router by providing username and password can set enable and secret password, etc. 

- **Interface Configuration Mode** : In this mode, only the configuration of interfaces is done. Assigning an IP address to an interface, bringing up the interface are the common tasks done in this mode. 

|Modes|	Access method|Prompt|Exit method|
|:---:|:---:|:---:|:---:|
|User Execution Mode|login|Router>	| Use logout command|
|Privilege Mode	|Use enable command in user mode	|	Router#| Use disable command to enter user mode| 
|Global Configuration Mode|Use configure terminal command	|Router(config)#|Use the exit command to enter into privilege mode|
|Interface Mode	|Use interface command and specify an interface in global configuration mode	|Router(config-if)#|Use the exit command to enter into global configuration mode or use the end command to enter into privilege mode.|

After that, let's do this configration one by one.

## Set Clock And Time Zone

Firstly, we must pass on to enable mode. Then, type  `set clock` command.

![clock](https://user-images.githubusercontent.com/87646106/216663831-0c7e06d8-6d7c-418f-af7b-857eae727451.png)

## Switch Configration

## End Point Device Configration

After connecting an endpoint device to the network device with a cable, the first thing you need to do is to make the necessary configurations to the endpoint devices. The first of these configurations is to **assign an IP and subnetmask** to the device and to **give the IP of the default gateway**.

In this topology 

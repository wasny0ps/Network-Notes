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

Firstly, we must pass on to privilege mode. Then, type  `clock set` command.

<img  src="https://github.com/wasny0ps/Network-Notes/blob/main/0x5%20-%20Router%20%26%20Switch%20Configration/source/clock.png" >

## Change Router Hostname

Change CLI mode is global configuration mode. And use `hostname` command.

<img height="50" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x5%20-%20Router%20%26%20Switch%20Configration/source/hostname.png" >

## Give Enable Mode Password

Enable password is used to limit the actions to be taken on the router to only certain people. You can give enable password by typing `enable secret yourpassword`. 

<img width="250" src="https://github.com/wasny0ps/Network-Notes/blob/main/0x5%20-%20Router%20%26%20Switch%20Configration/source/enable.png" >

Thereafter, when we want to pass on to privilege mode, router ask us enable password.

> While the enable password is stored as plain text in the running-config file, the enable secret is kept in a hashed state. For this reason, it is recommended to use the enable secret.

## Assign IP And Subnet Mask

In order for the router to communicate with the network and end devices, IP and subnetmask must be given to the leg of the network where it is located.

<img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x5%20-%20Router%20%26%20Switch%20Configration/source/ip.png" >

## Give Console Password

Generally console password is given when connect the device with console cable (rollover cable). As usual as console configuration is done in global configuration mode with local credentials. 

<img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x5%20-%20Router%20%26%20Switch%20Configration/source/console.png" >


## Telnet Configration

Telnet connection is used for remote access to the router. Telnet configuration is done in global configuration mode. FIrst of all, we must set username and password for telnet connection. Secondly, we should define how many users can access with telnet to router.

<img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x5%20-%20Router%20%26%20Switch%20Configration/source/telnet.png" >

## SSH Configration

They are used for the same purposes as SSH, telnet. Nevertheless, **SHH is more secure way to remote access than telnet**. Therefore, it is recommended to use the SHH while remote access to devices. The first step of SHH configration is create id_rsa file, which is SSH key use for authenticate the identity of a user or process that wants to access a remote system using the SSH protocol, with generate a crypto key, **which is RSA algorithym combination of domain name and router's hostname**. The second thing is defined id_rsa file size and use ssh version 2.

<img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x5%20-%20Router%20%26%20Switch%20Configration/source/ssh.png" >


## NVRAM Configration

Sometimes we want to save copy of our running-config to startup-config. In this case, we can copy running-config to NVRAM.

<img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x5%20-%20Router%20%26%20Switch%20Configration/source/nvram.png" >

<!--## FTP And TFTP Configration

All companies want to backup and save their routers and switches. In this scenario, most of the time backups are sent to ftp or tftp server. So, it is important to know how to copy the router configuration file to the server.-->



## Switch Configration

## Vlan Configration

Vlans are networks created within a local network. Thus, you can completely isolate these networks from each other by dividing your local network into parts. Companies often use this method to ensure security between networks within the company.

<img src="https://github.com/wasny0ps/Network-Notes/blob/main/0x5%20-%20Router%20%26%20Switch%20Configration/source/switch.png" >


## End Point Device Configration

After connecting an endpoint device to the network device with a cable, the first thing you need to do is to make the necessary configurations to the endpoint devices. The first of these configurations is to **assign an IP and subnetmask** to the device and to **give the IP of the default gateway**.

In this topology 

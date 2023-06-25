# Access Control Lists

Access Control Lists (ACLs) are one of the **security and control mechanism used in routers**. They mainly **filters incoming and outgoing traffic** coming to a router or going from it. In other words, with the help of access list control, we can filter traffic coming from any where and going to any where. For example, with an access control list, we can deny some users to access a specific server or service. Or we can allow only the people in a specific network to use FTP towards another network. Or we can limit one network to ping another. There can be many combinations and different ACL lines according to your need. Also, there is lots of benefits using ACL in networks. Here is some examples of them:

- **Improve network performance**.
- **Provides security as the administrator can configure the access list according to the needs and deny the unwanted packets from entering the network**.
- **Provides control over the traffic as it can permit or deny according to the need of the network**.

There are different access control list types used in networking. Each of them is used for various purposes and needs. According to your need, you can use one of these access list.

- **Standard Access-Lists**
- **Extended Access-Lists**
- **Named Access-Lists**

ACLs are created according to their type and each line after this creation is suitable to this type. This means that, if you are using standard ACLs, you can use only source addresses in the lines of ACLs. Or if you use extended ACL, you can use source, destination addresses and protocol or port information.

## Standard ACL

Standard Access-Lists are the ACLs which **uses only source addresses of the traffic**. In other words, they **filter the traffic according to their source**. ACL numbers **1-99** and 1300-1999 are used for standard access control lists. **Standard ACLs are added close to the destination**.

## Standard ACL Configuration

To create an standard access list on a router, the following command is used from the router’s global configuration mode:

```
Router(config)# access-list ACL_NUMBER permit|deny IP_ADDRESS WILDCARD_MASK
```

You can also use the host keyword to specify the host you want to permit or deny:

```
Router(config)# access-list ACL_NUMBER permit|deny host IP_ADDRESS
```

Once the access list is created, it needs to be applied to an interface. You do that by using the `ip access-group ACL_NUMBER in|out` interface subcommand. **'in' and 'out' keywords specify in which direction you are activating the ACL**. **'in' means that ACL is applied to the traffic coming into the interface**, while the **'out' keyword means that the ACL is applied to the traffic leaving the interface**.

Let's consider that we have a topology like this picture. We want only developers can access to the server. This means we don't want to users wouldn't get access to the server. For this reason, we will create a standard ACL on the router.

<p align="center"><img height="500" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x1%20-%20Access%20Control%20Lists/src/standard_ACL_topology.png"></p>

First of all, you must do RIP configuration on routers. If you don't how to configure it, you should [check this directory.](https://github.com/wasny0ps/Network-Notes/tree/main/0x8%20-%20Dynamic%20Routing)

After then, we want to allow traffic from the developer LAN to the server. First, we need to write an ACL to permit traffic from LAN 192.168.10.0/24 to server. We can use the following command on the router:

```
Router(config)#access-list 1 permit 192.168.10.0 0.0.0.255
```

The command above permits traffic from all IP addresses that begin with 10.0.0. We could also target the specific host by using the host keyword:

```
Router(config)#access-list 1 permit host 192.168.10.2
Router(config)#access-list 1 permit host 192.168.10.3
```
Next, we will deny traffic from the Users LAN:

```
Router(config)#access-list 1 deny 192.168.20.0 0.0.0.255
```

Next, we need to apply the access list to an interface. It is recommended to place the standard access lists as **close to the destination as possible**. In our case, this is the Gi0/0/0 interface on the router. Since we want to evaluate all packets trying to exit out Gi0/0/0, we will specify the outbound direction with the out keyword:

```
Router(config)#int gi0/0/0
Router(config-if)#ip access-group 1 out
```

Let's pinging to server from the different network's computers for check the configuration.

<p align="center"><img  src="https://github.com/wasny0ps/Network-Notes/blob/main/1x1%20-%20Access%20Control%20Lists/src/pinging.png"></p>

We done successfully. Also you can validate your ACL with `show ip access-list <acl-number>` command. What is more, you can get this topology from [here.](https://github.com/wasny0ps/Network-Notes/blob/main/1x1%20-%20Access%20Control%20Lists/src/Standard_ACL.pkt)

```
Router#show ip access-lists 1
Standard IP access list 1
    permit 192.168.10.0 0.0.0.255 (4 match(es))
    permit host 192.168.10.2
    permit host 192.168.10.3
    deny 192.168.20.0 0.0.0.255 (4 match(es))
```

## Extended ACL

Extended Access-Lists are enhanced versions of standard ACLs. In Extended ACLs, **source, destination addresses, port numbers and protocol types are used to filter the traffic**. ACL numbers **100-199** and 2000-2699 are used for extended access control lists. **Extended ACLs are added close to the source**.

## Extended ACL Configuration

Two steps are required to configure an extended access list:

- Configure an extended access list using the following command.

```
Router(config)#access list NUMBER permit|deny IP_PROTOCOL SOURCE_ADDRESS WILDCARD_MASK [PROTOCOL_INFORMATION] DESTINATION_ADDRESS WILDCARD_MASK PROTOCOL_INFORMATION
```

- Apply an access list to an interface using `ip access-group ACL_NUMBER in | out` command.

To better understand the concept of extended access lists, consider the following example:


<p align="center"><img height="250" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x1%20-%20Access%20Control%20Lists/src/extended_acl_topology.png"></p>

In this example, we want to **Users access only the server's web service**. **The developer access only server's FTP service**. And **Hacker's pc shouldn't get access to any service of this server**. First, we need to allow traffic from users to the server port of 80. We can do that using the following command:

```
Router(config)#access-list 100 permit tcp 192.168.10.2 0.0.0.0 172.160.10.2 0.0.0.0 eq 80
```

By using the tcp keyword, we can filter packets by the source and destination ports. In the example above, we have permitted traffic from 192.168.10.2 (Users workstation) to 172.160.10.2 (Server) on port 80. The last part of the statement, eq 80, specifies the destination port of 80. Since at the end of each access list there is an implicit deny all statement, we don’t need to define any more statement. After applying an access list, every traffic not originating from 192.168.10.2 and going to 192.168.0.1, port 80 will be denied.

After than, let's allow traffic from developer to the server port of 21. We can do that using the following command:

```
Router(config)#access-list 100 permit tcp 192.168.10.4 0.0.0.0 172.160.10.2 0.0.0.0 eq 21
```
Then, time to deny unauthorized IP addresses from unauthorized server's ports. We can do that using the following commands:

```
Router(config)#access-list 100 deny tcp 192.168.10.4 0.0.0.0 172.160.10.2 0.0.0.0 eq 80
Router(config)#access-list 100 deny tcp 192.168.10.2 0.0.0.0 172.160.10.2 0.0.0.0 eq 21
```

As always, we have to blocked server connection which comes from the hacker. So we must deny all ports in this server from the 192.168.10.3 (Hacker's IP Address) for security policy of our network. We can do that using the following command:

```
Router(config)#access-list 100 deny ip 192.168.10.3 0.0.0.0 172.160.10.2 0.0.0.0
```

Lastly, we should setting access list's bound way. We can do that using the following commands:

```
Router(config)#int gigabitEthernet 0/0/0
Router(config-if)#ip access-group 100 in
```

End of the configuration, there is checkimg time. Let's put to ping test.

<p align="center"><img  src="https://github.com/wasny0ps/Network-Notes/blob/main/1x1%20-%20Access%20Control%20Lists/src/extended_ping_test.png"></p>

As result shows that there is any device didn't ping to server because of almost all protocols are blocked by the our extended ACL. Let's look at other test result!

<p align="center"><img height="275" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x1%20-%20Access%20Control%20Lists/src/extended_web_page_test.png"></p>

<p align="center"><img height="250" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x1%20-%20Access%20Control%20Lists/src/extended_ftp_test.png"></p>

In both photos show, our topology rules are work properly. Why don't we look at from the hacker's view?

<p align="center"><img height="125" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x1%20-%20Access%20Control%20Lists/src/extended_web_page_test_hacker.png"></p>

<p align="center"><img height="300" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x1%20-%20Access%20Control%20Lists/src/extended_ftp_test_hacker.png"></p>

In last two photos says, there was nothing be on the rails for him. He don't get access to web and file service which is our configuration plan. And finally, you can get this topology from [here.](https://github.com/wasny0ps/Network-Notes/blob/main/1x1%20-%20Access%20Control%20Lists/src/Extended_ACL.pkt)

## Named ACL

Named Access-Lists are the ACLs, which **uses ACL names instead of ACL numbers**. **They can be used with both Standard and Extended ACLs**. These type of ACLs are **more memorable because of the explanatory names**.

## Named ACL Configuration

The named ACL name and type is defined using the following syntax:

```
Router(config) ip access-list STANDARD|EXTENDED NAME
```
The command above moves you to the ACL configuration mode, where you can configure the permit and deny statements. Just like with numbered ACLs, named ACLs ends with the implicit deny statement, so **any traffic not explicitly permitted will be forbidden**. In this configuration, we will use the following network in our configuration example:


<p align="center"><img height="200" src="https://github.com/wasny0ps/Network-Notes/blob/main/1x1%20-%20Access%20Control%20Lists/src/named_ACL_topology.png"></p>

We want to deny the user’s workstation any type of access to the domain server. We also want to enable the user unrestricted access to the file share. First, we will create and name our ACL:

```
Router(config)#ip access-list extended allow_file_share
```
Once inside the ACL config mode, we need to create a statement that will deny the user’s workstation access to the domain server:
```
Router(config-ext-nacl)#20 deny ip 10.0.0.2 0.0.0.0 192.168.0.2 0.0.0.0
```

The number 20 represents the line in which we want to place this entry in the ACL. This allows us to reorder statements later if needed. Now, we will execute a statement that will permit the workstation access to the file share:

```
Router(config-ext-nacl)#50 permit ip 10.0.0.2 0.0.0.0 192.168.0.3 0.0.0.0
```

Lastly, we need to apply the access list to the Gi0/0/0 interface on the router:

```
Router(config)#int gi0/0/0
Router(config-if)#ip access-group allow_traffic_fileshare in
```
The commands above will force the router to evaluate all packets trying to enter Gi0/0/0. If the workstation tries to access the domain server, the traffic will be forbidden because of the first ACL statement. However. if the user tries to access the file server, the traffic will be allowed, because of the second statement. Our named ACL configuration looks like this:

```
Router#sh ip access-lists 
Extended IP access list allow_file_share
    20 deny ip host 10.0.0.2 host 192.168.0.2 (2 match(es))
    50 permit ip host 10.0.0.2 host 192.168.0.3 (2 match(es))
```

Notice the sequence number at the beginning of each entry. If we need to stick a new entry between these two entries, we can do that by specifying a sequence number in the range between 20 and 50. If we don’t specify the sequence number, the entry will be added to the bottom of the list. Let's pinging to server from the different network's computers for check the configuration. Here is an image with proof that our named ACL configuration is working correctly. Finally, you can get this topology from [here.](https://github.com/wasny0ps/Network-Notes/blob/main/1x1%20-%20Access%20Control%20Lists/src/Named_ACL.pkt)

<p align="center"><img height="60"  src="https://github.com/wasny0ps/Network-Notes/blob/main/1x1%20-%20Access%20Control%20Lists/src/valideting.png"></p>

**by wasny0ps_**

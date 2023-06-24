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


## Extended ACL

Extended Access-Lists are enhanced versions of standard ACLs. In Extended ACLs, **source, destination addresses, port numbers and protocol types are used to filter the traffic**. ACL numbers **100-199** and 2000-2699 are used for extended access control lists. **Extended ACLs are added close to the source**.

## Extended ACL Configuration

## Named ACL

Named Access-Lists are the ACLs, which **uses ACL names instead of ACL numbers**. **They can be used with both Standard and Extended ACLs**. These type of ACLs are **more memorable because of the explanatory names**.

## Named ACL Configuration

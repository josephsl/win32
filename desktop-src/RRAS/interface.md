---
title: Interface
description: An interface is a logical connection to a network. Each interface is identified by a unique index. Multicast routing protocols (such as MOSPF) deal with all types of interfaces similarly.
ms.assetid: '593e3b8a-6f26-47c6-aa93-520d36db7a6f'
---

# Interface

An interface is a logical connection to a network. Each interface is identified by a unique index. Multicast routing protocols (such as MOSPF) deal with all types of interfaces similarly.

In the case of a LAN interface, the interface corresponds to an actual physical device in the computer (the LAN adapter). In the case of a WAN interface, the interface is mapped to a port when a connection is established. WAN interfaces can be based on tunnels and the port could be a virtual private network (VPN) port.

Windows 2000 and later operating systems support a "point-to-multipoint" interface. This type of interface can be viewed as a collection of point-to-point links that share a single termination point.

To uniquely identify an exact link in a point-to-multipoint interface, the MGM API uses the next hop address of the interface ID. To support this identification, the MGM API uses an extended interface ID, which includes a [next hop](next-hop.md) address.

 

 




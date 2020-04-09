# ND

see IPv6

Network Discover, Router Solicitation （探索） &amp; Advertisement （通告）

IPv6 結合了 IPv4 的 ARP 與 ICMP 及 Redirect。除了改良了 IPv4 版本也追加了 ND 新功能，此一功能能夠探測鄰近路由是否可到達。
   
                                /                                         \
                               /                                           \
                              /                                             \
                             /                                               \
                            /                                                 \
         Host ----- RS (Solicitate) ------------   -------------(Advertisement) RA  Router
                            \                                                 /
                             \                                               /
                              \                                             /
                               \                                           /
                                \                                         /


ND defines how to detect unreacheachability using NUD schematics:

1) to track NUD.

2) to solicitate which Neighbor Router is able to redirect datagram.

3) to check subnet mask (prefix).

4) stateless 無接縫.

5) to detect the modified data-link layer addr.

6) (omit)

7) (omit)

ND specifies the spec of Host & Router. Including: (RFC 4861)

* ND, Neighbor Discovery

* RD, Router Discovery

* AR, Address Resolution

* NUD, Neighbor Unreachability Detection

* DAD, Duplicate Address Detection

* ICMP Redirection

Weakness of ND see RFC 6583

ND is easier to be attacked by DOS, since its Router can be forged to be Default GW and advertise this forged info to other Routers in same Subnet (same prefix or same network mask).

# SND

Secure Neighbor Discovery

to avoid DOS by implementing RA (Router Advertisement) Guard, to filter the orifinal router in Link-state layer via ND header.

ND exposes its weakness due to Fragmentation, so SND rules out that fragment is banned. 

# Neighbor Cache  (table) & Destination Cache

this cached table shows out 

1) the datagram queue is reached to des or not.

2) reachable Neghibour.

3) process called if NUD (unreachable) Events happens.

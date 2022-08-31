Classifier before the data plane

Control plane or data plane function

The control plane is the part of a network that controls how data is forwarded, while the data plane is the actual forwarding process.

Routing protocols - control plane

Hardware vs slowpath

ICMP - much more than just pinging

TTL- time to live packets
- Can end up in a loop
	- Define number of routers it can be sent between
	- So if it reach 0 it will be thrown away

IP header validation
- Checksum to check for validation
- Just a hash function
- Usually in the hardware

Applications (UDP, TCP, DHCP) withing the router
- We might want to an ssh, or config


Update the TTL field


Some ICMP functions might be realized in the fast path (aka data plane), while others are put in the slow patch (aka control plane)

SDN (Software-defines network)
Parser - classifier


P4
- The catch is the static
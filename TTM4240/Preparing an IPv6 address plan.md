Section 1,2 and 4
## Section 1
Need to use IPv6, because almost run out of IPv4 addresses

## Section 2
2001:0db8:0000:0000:0000:0000:0000:0001 = 2001:db8::1

##### Grouping Addresses
2001:db8::/32
Contains all addresses from
- 2001:0db8:0000:0000:0000:0000:0000:0000
To
- 2001:0db8:ffff:ffff:ffff:ffff:ffff:ffff


![[Pasted image 20220902230341.png]]

## Section 4 - Preparing an Address plan
#### Basic structure of the Address plan
We can assign addresses per use type or per location, or combinations
![[Pasted image 20220903164428.png]]
- 4bits are assigned to Location (L)
	- Max 16 locations can be addressed
- 4bits to use type (T)
	- Each location having 16 (4 bits) allocatable use types
- Remaining 8bits (B)

#### IPv6, NAT and firewalls
NAT is used to allow multiple hosts to gain access to the publix internet using a single IPv4 address. IPv6 doesn't need NAT

Side effect of NAT is that it prevents unsolicited packets from internet from reaching hosts behinde NAT. Protocols that require two hosts that both reside behind NAT to communicate directly (peer-to-peer protocols) need to employ workarounds to set up communication through NAT. IPv6 applications may not have these workarounds built in, or not compatible with IPv6. So often more IPv6 problems with NAT.

Setting up a firewall is smart to prevent unwanted packets reaching hosts 

### Routers vs Firewall: Location or use type first
#### Location first
When the location is the primary subnet, each building, department etc. is assigned a number of dedicated addresses.
- All the networks within a single location will be aggregated to a single route in the routing table, so that the routing table will remain compact.
#### Use type first
When the use type is the primary subnet, the routing optimisation described above is not feasible, because the use types are divided across a number of locations. However, in practice this will not be a problem with most routers.

The advantage of first grouping all subnets by use type is that it makes it much easier to implement a security policy. Most firewall policies are based on the type of use and not on the location of the network. This is why the firewalls often require only one policy per use type

#### Recommendation
Use-type-based primary subnets, easiest way to integrate with existing policies and procedures

### Determining the Address Space Required for the Address Plan
We can calculate the number of groups as follows: 
1. First determine the number of locations or use types within your organisation. Count each location or use type as one group. 
2. Increase this number by one group (required for the backbone and other infrastructure). 
3. If you choose to work with location-based primary subnets, add one extra group for all networks that do not have a fixed location. These are networks for VPNs and tunnels, for example. 
4. Add one or two groups to allow for future expansion.

Could set up something like this:
![[Pasted image 20220903175333.png]]

Example 1: Location-based subnet
- Number of locations:  Three groups
- Backbone and other infrastructure:   One group
- Non-location-based networks:   One group
- Future locations:   Two groups
- Total:  Seven groups
![[Pasted image 20220903175657.png]]
Round it up to the power of 2, this results in eight subnets

![[Pasted image 20220903181020.png]]
- 13 available bits (B)

Example 2:
- Number of use types (staff,students, guests, servers and VPNs): Five groups
- Backbone and other infrastructure: One group
- Future use types: Four groups
- Total:  Ten groups
![[Pasted image 20220903181150.png]]
- Results in 16subnets (2^4 = 16)
	- 12 available bits (B)
![[Pasted image 20220903181259.png]]

### Optional Secondary subnets
The remaining bits can be used for numbering secondary subnetworks within the selected address plan. If the primary subnets are location-based, multiple networks can be addressed by location, whereas if the primary subnets are use type-based, multiple student networks or server networks can be addressed, for example.

The remaining bits can also be used to combine subnets by location and use type. If the subnet is location-based
![[Pasted image 20220903181425.png]]
- Combining location and use-types is often very good to optimize the network
	- Easier to optimise routing tables, but more complicate with the design of the security policy
	- By putting use type first, it will be easier to apply firewall policies per use type

### Double check
Check for remaining bits after creating of the subnets

### Leeway
If not sufficient amount left of the subnet for e.g. VPN network, we can change the assginment of primary and secondary subents
![[Pasted image 20220903212828.png]]

### Legibility
If more addresses available we can make those IPv6 addresses more legible

In the example in this section, we used 3 bits per location and 4 bits per use type. However, the hexadecimal digits in the IPv6 address each represent 4 bits. So if the location or use type only needs two or three bits, it can be useful to make it 4 bits instead, and make IPv6 addresses easier to read. 

From this:
![[Pasted image 20220903213032.png]]

To this:
![[Pasted image 20220903213043.png]]
The four L bits are displayed as one hexadecimal digit in the IPv6 address, and the same for the four T bits
2001:db8:1234:LTBB::/64

### Flexibility for future growth
It is possible to keep the locations/use-types in the address plan empty for future scaling

### Using VLAN numbers
Using VLAN numbers in the address planning.
	- In networks where most subnets are VLANs and thus already have a VLAN number, this simplifies the administration of VLAN and subnet numbers, because now only one number has to be managed.
![[Pasted image 20220903215028.png]]
Since VLAN are written in decimal, and IPv6 addresses are in hexadecimal. We need to convert between these two

![[Pasted image 20220903220928.png]]
	- In this approach, as the use type and location do not appear in the IPv6 address, it will not be possible to optimise the security policies and routing tables unless this was planned for when assigning VLAN IDs. With hexadecimal encodings, four bits remain free for other purposes, such as encoding the location.

### VLAN Numbers That Encode Location/Use Type
- Combining the encoding of location and use-types with VLAN numbers
![[Pasted image 20220903221329.png]]
Or:
![[Pasted image 20220903221347.png]]
- Reduces the avaible bits left, so only small/medium sized organisations will be able to stick to such numbering plan
#### Reversing VLAN Notation in an IPv6 Structure
There are also options for reversing previously defined VLAN notations. If, for example, the VLAN numbers are assigned first by location and then by use type, it is still possible to assign the IPv6 addresses in the reverse order: first by use type and then by location.

In the following example of a VLAN structure, the hexadecimal notation of the VLAN number, location and use type is placed between parentheses:
![[Pasted image 20220903221519.png]]
In this example, the first 4 bits of the VLAN number identify the location. The remaining 8 bits describe the use type. By copying this directly to the IPv6 address, we are able to optimise the routing table, but not the security policy. The reason for this is that the location is at the start of the address while the use type follows it. However, if we wish to use the IPv6 addresses to optimise the security policies, the use type has to be at the start of the address. 

To arrange this, we can move the first 4 bits of the VLAN number (which describe the location) to the back to become the last 4 bits of the IPv6 subnet. The last 8 bits of the VLAN number (which describe the use type) can be placed in front of these.

#### Hexadecimal Notation
![[Pasted image 20220903223908.png]]

#### Decimal notation
![[Pasted image 20220903223923.png]]

### Addressing point-to-point links
If you use point-to-point links, using a /64 address may present problems in combination with certain router configurations. In some cases, unused addresses in the /64 system may be bounced back by the routers on either side of the link. Data packets sent to this address will thus be sent back and forth between the routers like ping pong balls. This places an unwanted burden on the network. It might therefore, be practical in some cases to configure a prefix longer than /64 for these links.
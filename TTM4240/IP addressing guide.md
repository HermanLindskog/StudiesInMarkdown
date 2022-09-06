IP-addresses are 32 bits
Four octets (1octet = 8bit)

##### Classes
Class A - the first octet in the network
Class B - the first two octets
Class C - the first 3 octets 

IPv6 are 128bits
![[Pasted image 20220902180950.png]]

##### Private ip-addresses
- 10.0.0.0– 10.255.255.255 (10.0.0.0/8), which allows the greatest flexibility with the equivalent of 255 Class B address spaces to be used as needed.
- 172.16.0.0– 172.31.255.255 (172.16.0.0/12), which allows for 16 Class B address spaces. 
- 192.168.0.0– 192.168.255.255 (192.168.0.0/16), which allows for one Class B address space.

#### Subnetting
172.16.0.0/12
- /12 = 255.240.0.0
	- 255.255.255.255 - 255.240.0.0 =0.15.255.255
		- 172.16.0.0 - 172.31.255.255

##### VLMS (Variable Length Subnet Masks)
- Create a larger subnet of more than 255 host addresses
- Create very small subnets for WAN links
- Configure loopback addresses

#### Summarization
Summarizing IP-addresses ensures that there are no entries for child routes, which are routes that are created for any combination of the individual IP addresses conatined within a summary address in the routing table.
- Will reduce the number of routes that a router advertises to its neighbor

#### IP multicast
IP Multicast is a bandwidth conservation technology that reduces traffic and server loads by allowing a single stream of information on the network to be received by thousands of users. Applications that take advantage of multicast technologies include:  
- Video conferencing 
- Corporate communications 
- Music on hold IP Addressing Basics 6
- Distance learning 
- Distribution of software, stock quotes, and news

#### IP addressing in the smart business architecture
One example:
![[Pasted image 20220902210009.png]]
![[Pasted image 20220902210215.png]]
Important to take into considerations:
- Subnet size
- Subnet assignments
- Statis address assignments for network devices
- Dynamic address assignments

## How to do it
### Procedure 1
**Step 1**
*Create standards for IP address assignments within each subnet*
- For ease of identification, VLANs can be created to match the third octet of the IP subnet plus 100. For example: x.x.71.x. is assigned VLAN 171.
- Routers, gateways and hot standby router protocol (HSRP) virtual addresses within a subnet are assigned the first available addresses within the range.
- Printers and other fixed address assignments.
- DHCP addresses
- Routers may be assigned the .2 and .3 addresses, and the HSRP address assigned the .1 address. 
- Printers may be assigned the .5 through .9 addresses. 
- DHCP may rangefrom.10 through .250 addresses.

**Step 2**
*Define a consistent, structured naming convention and DNS for devices.*
- Create a consistent access point to routers for all network management information related to a device. 
- Reduce the opportunity for duplicate IP addresses. 
- Create simple identification of a device showing location, device type, and purpose. 
- Improve inventory management by providing a simpler method to identify network devices. 

**Step 3**
*Identify DHCP ranges and add them to DNS, including the location of the users. This range may be a portion of the IP address or a physical location. An example might be dhcp-bldg-c21-10 to dhcp-bldg-c21-254, which identifies IP addresses in building C, second floor, wiring closet 1. Alternatively, the precise subnet or variation thereof can be used for identification.*

**Step 4:** 
Document all standards that you develop and reference them on all network engineering plan documents to help ensure consistent deployment.

### Procedure 2
**Step 1**
*Determine which address space to use by evaluating all of the user and server requirements.*
- If you have the luxury of starting from scratch, consider the 10.0.0.0 range to allow for the most flexibility. The 10.0.0.0 range allows for many more hosts in the same range, which provides more flexibility when subnetting. For example: Each branch or building needs to have a consistent host range and the 10.0.0.0 network provides this flexibility.
- It is advisable not to start at the beginning of the range, to decrease the chance of address conflicts.

### Procedure 3 - Allocate IP space
**Step 1**
*Carefully define the size of the IP space with public addresses as it is available only in a finite amount.*
- Private addresses are not constrained 
- For ease of use, a /24 mask should be used as a minimum for user subnets. 
- End devices always grow in number, so there is no reason to set a low limit on the number of private addresses, since they are readily available. 
- WANconnections have much smaller requirements for IP addresses. In general, a point-to-point network connection between two sites has two IP addresses in use. If HSRP is used with redundant routes on each side, the number of addresses increases to six, three for each side of the link.– /30 subnet allows for two usable IP addresses– /29 subnet allows for six usable IP addresses

**Step 2**
*Reserve a subnet for physical security. These requirements can be assimple as asubnet to control door access to a building or something more complex like video surveillance for the entire building. Even if physical security is not required at the initial setup, you should still complete this step.*

**Step 3**
*Reserve a subnet for facilities. This subnet addresses physical plant requirements such as remote power control, air conditioning, and facilities monitoring, which can now be monitored with new technology on the IP network. *

**Step 4**
*Allocate public addresses for all production networks in the demilitarized zone (DMZ), which is the network or networks situated between an ISP edge router and corporate firewalls. An alternative is to use NAT.*

**Step 5**
*Allocate a subnet for Remote Access, which is generally set up as a virtual private network (VPN).*

**Step 6**
*Allocate a subnet for Network Management to provide access to network devices such as Ethernet switches, firewalls, routers, etc. This subnet will allow for easy management with a separate logical network. Cisco SBA uses VLAN1formanagementofnetwork devices.*

**Step 7**
*Create a loopback address to make it easier to manage a single address for a router with multiple interfaces*

Loopbacks:
- Always up
- Reachable if one goes down
- Provide single source address for voice applications, network management, routing etc..
- Advertised by the IP routing protocol

### Procedure 4 - Document plan
Document all your workt to further scale it up/down and use your documentation if anything goes wrong

## Process - Maintaining and Growing Network Space
1. Resolve Overlapping Address Ranges 
2. Increase the Number of IP Addresses 
3. Mergewith Another Company
### Procedure 1 - Resolve Overlapping Address Ranges
First scenario:
- Same range, but different subnet. They can communicate, but not optimal
**Step 1**
Remove summarization from both sides if it contains any of the overlapping IP space.

**Step 2**
Renumber the overlapping space.

**Step 3**
Reinstate the summarization.
![[Pasted image 20220902220532.png]]

Second scenario:
- Spaces conflict, uses the same subnet
![[Pasted image 20220902220650.png]]

**Step 1**
Use NAT from the conflicting site in a new nonconflicting IP address space as atemporary workaround

**Step 2**
Renumber the conflicting space.

**Step 3**
Once the hosts are renumbered into the new address space, turn NAT off.

### Procedure 2 - Increase the number of IP addresses
Increase the subnet and use DHC
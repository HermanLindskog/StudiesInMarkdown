### First words
A system has *functional* and *non-functional properties* 

*Functional* properties of a car: 
- Transport poeple and gods for one place to another

*Non-functional properties*:
- Maxium speed 
- Wheter the car starts or not
- Break down when driving
- Causing accidents

Performance (carrying capacity, speed), Dependability (the car starts and fullfills its function)

For ICT-systems, performance and dependability characteristics would include:
- Whether the service is up and running when needed, i.e. its availability; this includes the availability of all the components the system relies on. 
- Whether resources are sufficient in the network and at the end-user station, e.g. whether a request will be lost or not. 
- How long it takes to establish a session, i.e. the setup time. 
- Whether the service is provided non-interrupted during the entire session, i.e. its reliability. 
- Whether the real-time requirements for user interactions (approx. 100 ms) are fulfilled, i.e. the end-to-end delay. 
- Whether the participants receive the data transmitted, i.e. the loss rate and the integrity of the received da

## What it is all about
Some models can be applied to manye different systems, like queuing models to determine:
- The internal job flow and response times in a computer system with central processors, disks, caches, memories, input/output modules etc. ;
- The packet flow and end-to-end delay in a packet switched computer network; 
- The probability that there is no repairman available when a module needs repair and the duration of the out-of-service period.

Evaluation cycle for a system
![[Pasted image 20220829114414.png]]
### The system
System can be defined as a *regularly interacting* or *interdependent group of items forming a unified whole*

#### Systems components
Could be:
- Processors with their processing capacity (MIPS)
- Hard disk with storage capacity (Mbytes), and an access time (s), and transfer rate (Mbytes/s)
- Transmission channels with a transmission capacity measured in kbits/s or Mbits/s
	- Buses inside a processor, or
	- Communication links between nodes in a network
![[Pasted image 20220829115823.png]]
	*Factors to considerate when modeling an ICT-system*

#### Structure
![[Pasted image 20220829121109.png]]
	*Model of a 2B(64 kbit/s)+D(16kbit/s) ISDN access. D-channels used for singaling first, and then B-channels for communication*

The structure is about how the resources in the system should be utilized in order to deliver the service og which the dependability and/or performance properties are evaluated.

Dependability models:
- How system components works that enable the system to deliver its services and work
- The structure
Performance models:
- Uses a combination of system components to make it easier to understand
- How the system components/resources are used
	- Sequentially or concurrently

Structure of a systems may be:
- Physical 
	- How nodes are interconnected
- Logical
	- Units attached to physical buses cooperate. Used as a logical ring or hierarchically with master and slaves
- Derived from the physical and/or logical

#### Behavior
1. Queueing disiciplines
	1. FIFO
	2. LIFO
	3. SJF, etc..
2. Protocols
3. Other traffic mechanisms apart from protocols
	1. Routing algorithms
	2. Call admission control (CAC) and User parameter controll (UPC)
4. Fault-handling mechaninsm which encompass error detection, localization and isolation and varoius techniques to provide fault tolerance and automatic and manual fault removal (repair)


### The users and the envrionments
#### Load profile
This is called traffic
![[Pasted image 20220829123714.png]]
	*Shape of the traffic at different time scales*

![[Pasted image 20220829124122.png]]
![[Pasted image 20220829124224.png]]

#### Operations and maintance
Must only be taking into account only if they affect the traffic handling, which could be:
- Configuration control
	- Dynamically change the available transmission capacity between nodes in the network depending on time of the day or the offered traffic
- Traffic control
	- reject traffic at an early stage of an Intelligent Network (IN) service interaction when the network is already congested

Actions (either manually or automatic) taken depending on the load, must also be considerated. We could try to identify or quantify the impact of different operation and maintenance strategies and traffic load.

Operation and maintance functionality includes:
- Configuration control
	- Ensure enoug spare transmission capacity between nodes so that traffic can be re-routed in case of failure
- Fault-handling
	- detect whenever a router fails and localize the part of the router that has failed, re-route traffic, repair (fault removal) the faulty part, restart and test the repaired part, and finally route traffic again through the router


![[Pasted image 20220831084514.png]]
	*A typical picture of maintance*

### Concepts and terminology
#### Quality of service
![[Pasted image 20220831085704.png]]
	QoS explained in a picture
Definition: "Degree of compliance of a service to the agreement that exists between the user and the provider of this service"

#### Compound systems


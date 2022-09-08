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
![[Pasted image 20220901141619.png]]

## Dependability
Definition:
**"Trustworthiness of a system such that reliance can justifiably be placed on the service it delivers."**

Threats to depenability:
1. Failure
	**Deviation of the delivered service from the compliance with the specification. Transition from correct service to incorrect service (e.g. the service becomes unavailable).**
2. Error
	**Part of the system state which is liable to lead to a failure.**
3. Fault
	**Adjudged or hypothesized cause of an error.**
![[Pasted image 20220901142222.png]]
![[Pasted image 20220901142246.png]]
- An electromagnetic pulse (fault) results in flipping of a bit in data register (error)
	- When this register is accessed, a wrong result is returned to the user (failure)

The conceptual distinction between fault, error and failure is very important. For example, the two basic approaches to achieve a dependable system are:
- fault prevention
- Fault tolerance

#### Types of fault
- physical faults
- Transient fault
	- These faults are present only for a short period of time and no physical change occurs in the system, e.g. external disturbances like electromagnetic interference and radiation.
- Intermittent (sporadic)
	- Come and go
- Design (logical)
	- Humad made faults during specification, design and implementation of a system
- Interaction or operational faults
	- Humans operating or mainting a system
- Faults caused by the environment

#### System times
The system is either:
- Working
- Failed (down)

I(t) is a function of time that describes the behavior of the system. 
	I(t) = {1 if the system is working at time t
			 { 0 otherwise
![[Pasted image 20220905132701.png]]

$$T_{FF}$$ Time to First Failure
$$T_{CF}$$ Time to first Catastrophic Failure.
$$T_{BF}$$ Time Between Failures
$$T_{U}$$Up Time
$$T_{D}$$ Down Time
$$T_{F}$$ Time to failure

MTFF =E(TFF) Mean Time to First Failure. 
MTCF =E(TCF) Mean Time to Catastrophic Failure. 
MTBF =E(TBF) Mean Time Between Failures6. 
MUT =E(TU) Mean Up Time. 
MDT =E(TD) Mean Down Time. 
MTTF =E(TF) Mean Time To Failure.

#### Availability
*"Ability of a system to provide a set of services at a given instant of time or at any instant within a given time interval."*

1. Asymptotic availability, denoted with A
	1. It is assumed that the system has reached its steady state and A is the probability of finding the system in a working state at a randomly chosen time in the future.
	$$t-> \infty \ A=limP(I(t)=1)$$
	$$A=\frac {MUT} {MDT+MUT} = \frac {MUT} {MTBF} $$
2. Often used to talk about unavavilability U insted, (asymptotic is close to one)
	$$ U=1-A=\frac {MDT} {MTBF}$$
	So it is often between 10^-1 and 10^-5
3. Instanteneous availability/pointwise availability, which is the probability that the system is working at a given instant t
	$$A(t)=P(I(t)=1)=E(I(t))$$
4. Interval availability or mean availability:
	$$\[A(t1,t2)=\frac {1} {t2-t1} \int_{t1}^{t2} A(t) \,dt\]$$
	$$\[A(t1,t2)=E\frac {1} {t2-t1} \int_{t1}^{t2} I(t) \,dt\]$$
5. Measure converge to the asymptotic availability, given that it exists
	A = lim
	t→∞ A(t) = lim
	t→∞ A(t, t + τ )

Availability measures are probabilities and expected values, bot what is observed at an instant or during a period of time.

#### Reliability
*"Ability of a system to provide uninterrupted service."*
Usually determined by the time to first faire $$T_{FF}$$
	Reliability function:
		R(t) = P (TFF > t)
	Can also measure it in Mean Time to First Failure

**System in steady state**

		When a telephone user makes a call, the network is in steady state, and the
	reliability is given by the probability that the call terminates before a failure occurs.
	R(t) = P (TF > t) 

#### Safety
"Ability of a system to provide service without the occurrence of catastrophic failures."
- Benign failures
	- Doesn't really count, and is is the probability that no catastrophic failure has occurred
	until and including time t.
- Catastrophic failures
	- Determined by the importance of the application

### Performance
"Ability of a system to provide the resources needed to deliver its services."

#### Capacity
"Maximum load a system can handle per time unit"
- The capacity is a property of a system, and not of the service it delivers.
- Denoted by C and could measure things like:
	- the capacity of a transmission channel (service provided at the physical level) is
	the number of bits transferred per second (datarate).
	- the capacity of a routing function in an IP-router is a number of packets per second.

#### Traffic and utilization
- Instantaneous carried traffic A′(t)
	- Number of busy resources in a pool of resources at a given instant of time t.
- Carried traffic A′(t)
	- Average number of busy resources in the time interval [0,T]
- Unit for traffic is Erland, and is dimensionless

![Alt text](/TTM4110/Images/Screenshot%20from%202022-09-08%2015-31-23.png "Example")

- Offered traffic
	- "Traffic that would be carried if the number of resources were infinite"
	- Greater or equal to the carried traffic
		- The difference between the
		offered traffic and the carried traffic is the lost traffic.

- Lost traffic
	- "Difference between the offered traffic and the carried traffic."
	- Not sufficient resources to serve the incoming service requests
		- Can also seperate between primary and secondary traffic
![Alt text](/TTM4110/Images/Screenshot%20from%202022-09-08%2015-49-12.png "Traffic")

#### Throughput
"Portion of the system capacity that is utilized by the users."
- Denoted by ζ
- Throughput is the portion of system capacity used by the user

#### Delay
"Time it takes to complete a service

#### System times - W
"Accumulated time a service request is pending for service in a system"
![Alt text](/TTM4110/Images/Screenshot%20from%202022-09-08%2015-59-40.png "System times")

#### System time - X
"Accumulated time a service request is served by a system."

#### Sojourn time - S
"Total time a service request is in a system
- Is the sum of the waiting time and service time (S=W+X)

#### End-to-end performance
- Interested in total delay from the sender to reciever, for instance for real-time services

### Relation between dependability and performance
- They are not independent from each other
	- While the depenedabilith could be:
		-  physical operating conditions,
		- operation and maintenance, and
		- offered traffic
	- Performance could be:
		- Traffic
		- Traffic interest
		- Traffic mix

### QoS specification
![Alt text](/TTM4110/Images/Screenshot%20from%202022-09-08%2016-27-09.png "QoS")

## Use of modeling in development and dimensioning

### Requirements and specifications


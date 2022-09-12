### Discrete-event simulation
*A discrete-event system is a system which behavior is governed by events occurring at discrete points in time and resulting in distinct changes of the state of the system.*

#### Intro to simulation
##### Advantages and disadvantages of simulation
- Flexible and practical
- A good understanding of how the system works with simulation modelling

##### Application areas
- Communication systems
	- Routing strategies, maintenance policies etc..
- COmputer
	- Performance of high performance computers or clusters
- Information systems
	- CLient/server architectures
- Verification of electronic circuits
	- Function, logic
- Wave progagation in a transmission channel
	- Propagation time
- Manufacturing systems
	- SPare parts stocks, just-in-time production, manual vs automated work
- Public systems
	- Military, health, natural resources
- Transportation systems
- COnstruction systems
- Restaurants

##### Type of simulation models
Static or dynamic, discrete or continuous, deterministic or stochastic
- **Static** (monte-carlo) represent a system at a particular point of time (rolling a dice). **Dynamic** is a system that is changing over time
- **Discrete**, variables change only at a discrete points in time (events). **Continuous**, the variables vary continuously in time, e.g. the propagation of an electromagnetic wave in space
- **Deterministic**, does not contain random variable. A given set of inputs result in a unique set of outputs, e.g. a “what-if” budget analysis in a spreadsheet. A **stochastic** simulation model contains one or more random variables as inputs which lead to random outputs. The output must therefore be treated as statistical estimates of the system characteristics.

##### Steps in a simulation study
1. Problem formulation and objectives
	1. Specify the objective, requirements and the problem
2. Model conceptualization
	1. All components that affects the system. Must understand and identify the details
3. Data collection
	1. Typical parameters for the resource, probability distributions
	2. Often time consuming and hard
4. Model translation
	1. Actually program the model in a simulation language or python
5. Testing
	1. Test the simulator
6. Experiments
	1. Check the simulation with different parameters
7. Post-processing
	1. The output must be parsed (. calculating statistics and values of interest, plotting graphs, etc), analyzed and interpreted

101 set up a simulation model:
![[Pasted image 20220910163619.png]]
#### Different types of simulation:
![[Pasted image 20220910165705.png]]
These types of simulation are either 
- Terminated
	- Stops after a certain time or given events
- Non-terminated
	- Not naturally terminated. ICT-systems are typically non-terminated

For **transient-state analysis**, terminating conditions are specified as a number of events or a time duration. While for **steady-state analysis**, the experiment must last long enough to ensure that the system has reached a steady state and data must be collected only when the system has reached a steady state.
- Hence, using observations made before the system has reached a steady state would bias the estimation. Therefore, when studying stationary properties the observations must start after a warm-up (transient) period.

### General principles of discrete-event simulation
##### Time-driven and event-driven simulations
- Time-driven simulation
	- May be efficient if the underlying process generates events at regular intervals, e.g. time-slotted systems, or if it is desirable to discretize a continuous process.
		- However, it is less suited when the time between events may be of arbitrary length since this may result in a large processing overhead (the system state is sampled even if no event occurs; useless samples) and in missing state changes (the system state is not sampled although it changes).
![[Pasted image 20220910221740.png]]

- Event-driven simulation
	- Skips the time when there is no change and only sample the system when events occur
		- The time between events does not affect the efficiency of event-driven simulations.
![[Pasted image 20220910221751.png]]

#### Concepts in discrete-event simulation
- System. A collection of entities that interact over time. 
- Model. An abstract representation of the system. 
- System state. A set of variables describing the system at a time t. 
- Entity. System component explicitly represented in the model. 
- Attribute. Property of an entity. 
- Event. Occurrence of change of the system state. 
- Event notice. Record of an event to occur. 
- Event list. List of event notices ordered by time of occurrence. 
- Activity. Specified time duration, e.g. drawn from a probability distribution. 
- Delay. Unspecified time duration, e.g. time in a queue. 
- Clock. Simulated time. 
- Resource. A passive object used by some entities to perform an activity.
![[Pasted image 20220910224307.png]]

##### Interaction between entities
Entities are key elements in the model
- Could be **static** (created at startup time and lasting during the entire simulation), or **dynamic** (created at startup time and terminated before the simulation is over or created during the simulation)

A simulator must include control functions to handle a large number of entities, e.g. mechanisms to passivate and re-activate entities, to queue entities pending, queues, lists or tables to enable events to occur in a certain order.
![[Pasted image 20220910230355.png]]

##### World views
Some approaches for world view or simulation modeling paradigm
- Activity scanning (time-driven)
	- The modeling focuses on activities and the conditions for an activity to start. The advantage of this approach is its simplicity which makes it easy to implement in a general programming language. Its main drawback is its inefficiency due to the repeated scanning of all the activities.
- Event scheduling (event-driven)
	- Focues on the events and requires a chronological list of future events to be maintained
- Process interaction
	- Focus on entities and their dependences and interactions. A process describes the behavior of an entity (sequence of activities, “life cycle”), its interactions with other entities and its use of resources. It requires a chronological list of future events to be maintained and synchronization mechanisms. A system can be partitioned in subsystems and the life cycle of each subsystem can be modeled separately which makes the process oriented approach attractive when modeling large systems.

#### Simulation tools
Selecting the right tools
##### Types of simulation tools
Describing the level of details

##### General purpose programming language
C, C++, Java, Python etc..

##### Simulation programming language
Specifically designed for simulation purposes

##### Criteria for specialized simulation tool selection
- Modeling. Which modeling methods can be used? What is the level of abstraction? Is hierarchical and modular model building possible? 
- Built-in models. Are there models that can be reused directly? For example protocols (e.g. ATM, TCP/IP, UDP, WAP), sources (e.g. phone calls, web traffic, video streaming, peer-to-peer traffic), failure processes (e.g. hardware failures, communication noise), routing protocols (e.g. OSPF, RIP) etc. 
- Simulation mechanisms. What types of simulation are supported? How are events and the event list managed (scheduling, list processing)? 
- Setup of a simulation experiment. Is it possible to easily set up both transient and stationary experiments? Is it easy to define start and stop criteria? Is it possible to specify the transient period? Is it possible to handle independent replicas? Is sectioning (batch-mean) supported? Is logging support provided? 
- Data collection. How good is the support for accumulating, tracing and presenting statistics? How easy is it to tailor the data collection and presentation? 
- Adaptability. How easy is it to add new models/functions or modify/extend the existing ones? Is it an open-source tool? 
- Efficiency. How CPU-demanding is the execution of a simulation using the tool? Is distributed simulation supported? 
- Usability. How good is the documentation (user guide and reference manual)? Is there any graphical input and/or output graphical front-end? Does it exist any interactive debugger? 
- Availability. How much does it cost? Under which license is it distributed? Which support is provided? Which hardware and software platforms are supported? What are the plans for future development? 
- Type of problem. Is the system that shall be simulated composed of standard components/protocols that shall be investigated for a (few) configurations and system loads, or is the study primarily aimed at investigating new mechanisms and/or system designs? How broad shall the study be? For instance, shall only packet flows in a network be studied, or does the study also include aspects like network management, fault handling, service handling and provision, logistics, etc. 
- Skill of the simulator developer/development team. This one should be obvious! However, a warning seems appropriate. Buying an expensive tool with claimed simplicity and user friendliness does not substitute insight and knowledge.


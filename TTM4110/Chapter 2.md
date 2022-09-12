# Fundamentals of probability
Distrubuted functions
- How different characteristics such as mean values and cariations can be calculated, and how dependencies between stochastic processes affect the results

## Probability calculation
### Probability
Experiments with a deterministic process, the outcome will be identical as long as the initial conditions remain the same
- If we believe it is randomness, we must use stochastic process and probability models

**Experiment**
*An experiment is any process or study whose outcome is random and that results in an observation. The set of all possible outcomes of an experiment is called the sample space and is denoted Ω*

Random generic
- Flipping a coin

**Event**
*An event is any outcome, or collection of outcomes, of an experiment. It is a subset of the sample space.*
- Is it head or tails, is our router using all its capacity
- We are interested in a set of the event



**Probability**
*The probability of an event is defined as its asymptotic relative frequency, i.e. when the number of experiments tends to infinity.*
- Relative frequency of (H, T, H) is 2/3
- Asymptotic is a number of times almost to infinity (many number of experiments)

Ω **sample space** 
$$N_Ω$$- Number of events in (cardinality of) Ω 
"A" set of events of interest 
$$N_A$$ - Number of outcomes A observed

#### Intersection and union
##### Intersection
In common with each other
##### Union
What A and B have for them self

##### Conditional probability
$$P(A|B)=\frac {P(A\cap B)}{P(B)}$$
- Betinget sannsynlighet

**Total probability**
P(A) = P(A∩B)+P(A∩ ¯B)=P(A|B)·P(B)+P(A|¯B)·P(¯B)
![[Pasted image 20220908221050.png]]

#### Bayes formula
![[Pasted image 20220908221332.png]]

Two type of variables
- Infinite ~ 
- Continious

r,v, X - distributed function (like gaussian)
discrete - random variable

## Distribution of random variables
### Continuous random variables
The sum of all the probabilites will become 1
- For cumulative distrubution function (cdf)
![[Pasted image 20220908223252.png]]
- Probability denstity function (pdf)
![[Pasted image 20220908224113.png]]

### Probability density function and cumulative distribution function
[[#Continuous random variables]]

#### Discrete random variable
*A random variable is discrete if the sample space is finite or infinite but countable*

![[Pasted image 20220908233520.png]]

### Probability distributions used in the description of ICT-systems
#### Negative exponential distribution (n.e.d.)
The probability density function of the negative exponential distribution, or simply exponential distribution is:
![[Pasted image 20220908234515.png]]
- All the time variables to calculate e.g. delay of a packet
![[Pasted image 20220909123745.png]]

#### Hypo-exponential distribution
- Sum of series connection of *k* independent exponentially distributed random variables that may have different rates

#### Erlang-k distribution
*A special case of the hypo-exponential distribution where the k random variables are identically distributed.*

![[Pasted image 20220909123538.png]]

#### Gamma distribution
Generalization of the Erland distribution 

#### Hyper-exponential distribution
![[Pasted image 20220909124954.png]]

#### Weibull distribution

#### Uniform distribution
![[Pasted image 20220909131033.png]]
a) Sketch the pdf for the continuous and pmd for the discrete case
![[Pasted image 20220909131123.png]]

#### Normal distribution

##### Relations between distributions
![[Pasted image 20220909131440.png]]

![[Pasted image 20220909131646.png]]

#### Bernoulli distribution
Either 0 or 1


pdf (density, continious variables) vs pmf (mass, discrete random variables)
pdf - gaussian distribution
pmf - e.g. dices. A value that a random number has the value

![[Pasted image 20220909132147.png]]

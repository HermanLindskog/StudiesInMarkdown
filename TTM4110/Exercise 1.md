1.1
a)
Figure 2a shows approxmitalely 50 users at the most.
To not become free it should be above 10Mbps
$$C_t=50*10Mb/s \ =500Mb/s$$
Figura 2b shows ca. 500 users at the most of news clips, but the quality should just be around 1Mb/s for the clips so it doesn't end up free
$$C_t=500*1Mb/s \ = 500Mb/s$$
Necessary storage capacity for archive clips shoulde be calculated a bit different. Should be available for 3 years = 3 x 365 days, and the quality should be sufficient to extract freeze frames. E.g. 100Mb/s
$$C_s=3*365days*10clips*600sec/clip*100Mb/s \ =6.57*10^{14}\ =82.13 Terabytes$$

1.2
b) 
*Using the graphs in Figure 3, give an upper bound on the ratio Lm MTFF , where Lm is the average playback length. Hint: start with choosing a reasonable value for a service failure and use the figure.*

- One failure is acceptable, so we could use the Figure for N ≤ 1. We could say that the probability that one or less failure occurs should be 90%
- 
$$P((N≤1)≥0.90\ -> playback length ≤ 0.55 *MTFF$$
- So the following ratio $$\frac {L_m} {MTTF}≤0.55$$

*Do the same for news clips and define MTCF for this service. How should the relation between MTTF and MTCF be?*
- They have defined that it should not occur any failure during playback of new clips, so look at the curve for N ≤ 0
$$P((N≤0)≥0.90\ ->playback\ length ≤0.1*MTFF $$
- So the following ratio $$\frac {L_m} {MTTF}≤0.1$$
MTCF needs to be very high, so maybe $$MTCF=100*MTFF$$

Exercise 1.2
*a) What is the packet loss probability $$P_p$$ in layer 3 given that the bit error probability in layer 2 is $$P_b$$ and assuming independent bit errors? Hint: the packet length is $$L_p$$ bits.*

- Packet lost if one or more bits is changed/destroyed. And all errors are independent
$$1-P_p=(1-P_b)^{L_p}$$
$$P_p=1-(1-P_b)^{L_p}$$
*b) Draw a message sequence diagram to illustrate how the ARQ protocol works in the case of an ideal transmission channel (no packet loss).*
- ![[Pasted image 20220902125938.png]]
*c) What is the probability that a packet is successfully received after one packet loss?*
- $$P_2=P_p*(1-P_p)$$
*After two consecutive packet losses?*
- $$P_3=P_p*P_p*(1-P_p)=P^2_p*(1-P_p)$$
*After n −1 consecutive packet losses? (give the probability in terms of Pp)*
- $$P_n=P^{n-1}_p*(1-P_p)$$
### Radio frequency
Tv, data, radio etc..
1. Transfer information
2. Sensing and detecting objects
	1. Radar and body 
3. Heating objects


#### About radio frequency
The lower, the more pentration it have
- Lower frequency will propagates longer distance
- AM and FM use MF to allow the singal to travel for longer distance and penetrate buildings
- Wifi will almost always use 2,4 or 5Ghz
	- Because we don't want it to travel that far away from us
- requency of an RF is based on the application


##### Spectrum
Range of frequencies
- not humanliy perspective


![[Pasted image 20220831122353.png]]

#### Frequencies for radio transmission
LS - used by submariens. Can go through water e.g.
MF and HF - medium or high frequency. Could be reflected at the ionosphere
	We need high transmit power
VHF and UHF
SHF - microwave and fixed satellite
EHG - infra red (IR) direct transmission


#### Frequency regulations
ITU is responsible for coordinate the activities
ITU-R holds auctions for the new frequencies and manages frequency bands over the world
![[Pasted image 20220831122802.png]]


#### Bands
Specific range of frequencies
Am used 550 - 1700 KHz
Fm covers 88 - 108 MHz
You often have to buy a license to use those bands
	But you also have unlicensed bands


## Signal propagation and antennas
#### Ground wave prograpation
Follows the contour of the earth
	long distance
	E.g. AM radio
#### Sky wave propagation
![[Pasted image 20220831123230.png]]


#### Line-of-sight propagation
Antennas that will send signal when they both are in line-of-sight
Mobile phones will this type
	Modifies line-of-sight
		Combination of effects like diffraction, mulipath reflection, local repeaters and rapid handoff
		Even thoug they do not have a clear line of sight, it will still work

#### Signal progagation ranges
![[Pasted image 20220831123548.png]]
- Transmission range
	- Communication possible
	- Low error rate
- Detection range
	- not able to do proper communication, signal not strongh enough
- Interferenca range
	- Signals may not be detected
	- Added to the ground noise

#### Antennas
Electrical conductor or system of conductors
Both send and transmit
Isotrpoic radiator
	Used as a refrence
The higher the wavelenght
	The sight of the antenna has to be high

1. Directed antennas
2. Sectorized antennas

## Channel capacity
A sender and receiver
Maxium rate of the signal is limited by imprairments such as noise

#### Concepts to channel capacity
Data rate - bits per second(bps)
The greater the bandwidth, the higher the information-carrying capacity

Signal bandwidth example
It is calculated with the highest bandwidth minus the smallest

#### Signal-to-noise ratio (SNR)
Ratio of the power in a signal to the power contained in the noise that's present at a particular point in the transmission

#### Nyquist bandwidth

#### Wireless channel capacity
Theoretical maximum that can be achieved

$$B_{2+3} $$

## Wireless transmisison: Impairments
 - Noise
 - Transmission loss
	 - Signal attenuation
 - Multipath
	 - Reflection, refraction and scattering
 - Doppler spread
	 - When the user is on the move

#### Effect of noise on a digital signal
![[Pasted image 20220831131237.png]]
- Some of signal is mixed because of the noise
	- Misunderstanding

#### Autenuation
- Strength falls off with distance
- Is greater at high frequencies
- Recieved signal
	- Sufficient strength so that the receive can interpret the signal
	- Must maintan a level off sufficiently higher than the noise

#### Free space loss
$$P_t/P_r$$

#### Signal propagatin
- Shadow
	- Obstacles
- Reflection
	- Reflects from big buildins
- Refraction
	- Depends on the density of the medium
- Scattering
- Diffraction
	- Sharp objects

#### Multipath propagaton
A reciever will recieve many different copies of the signal, so it makes sure that the signal will actyallu end up to the sender
	Intersymbol interference (ISI)
	Will arrive at the same time

#### Fading
A signal out of a transmittor radiayes into wide direction
- They tak different paths and arrive at the reciever at different timing and with different signal strength
Fading = Deterioration of the signal quality


#### Fast fading vs Slow fading
Rapid fluctuations of signal cause by movement (Doppler)
Coherence time $$T_c$$ is much bigger than bit time $$T_B$$
, the channel does not change during the bit time -> slow fading
Otherwise, fast trading
	Rate of change of the channel characteristics is larger than the rate of change of the transmitted signal

## Modulation
Digital signals cannot be directly transmitted in the radio medium
Transform the binary numbers to signals

#### Why do we need modulation?
Generate a modulated signal suited and compatible to the characteristics of the transmission channel

Synchronization desicision
- Decide where to start reading the signals from


#### Binary phase shift keying (BPSK)
Each symbol represent 1 bit

The relationship between the number of available symbols, M, and the number of bits that can be represented by a symbol, n, is: $$M = 2n$$
The amplitude will define the distance from the origin

#### Quadrature phase shift keying (QPSK)
Each symbol represent two bits
4 phase shifts are used




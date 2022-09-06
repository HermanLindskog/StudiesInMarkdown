#### Analog signal
Signal intensity varies in a smooth fashion over time
	No breaks

#### Digital signal
Constant level for some period of time and then changes to another constant level

![[Pasted image 20220831234714.png]]

#### Periodic signal
Analog or digital signal pattern that repeats over time $$S(t+T)=s(t)$$ $$-\infty < t < +\infty$$
Where T is the signal period

#### Sine wave parameters
$$s(t)=Asin(2\pi ft+\phi$$
f = frequency
t = given time
A = amplitude
$$\phi = phase\ shift$$
#### Frequency and wavelength
$$f=\frac1T$$
| Frequency | Period |
| --------- | ------ |
| 1MHz      | 1 µs   |
| 1KHz      | 1 ms   |
| 1Hz       | 1 s    |
**Frequency** - number of electromagnetic wave cycles that pass a single point per unit time. Measured in Hertz (Hz), which is number of cycles per second
**Wavelength** - distance that the signal travels during 1 complete cycle
**Period (T)** - time taken for one complete oscillation

#### Relation wavelength/freq
Speed of the wave is the distance that the wave travels per unit time
$$v=\frac \lambda T$$
$$v=f\lambda$$
For electromagnetic travellig through vacuum speed of the wave is $$3*10^8 \ m\ s-1\ (c)$$ $$c=f\lambda$$
#### Bandwidth
(bps) - Amout of data transferred
(Hz) - size of the transmission channel

#### Radio frequency
From 20 kHz to 300 GHz
![[Pasted image 20220901133842.png]]

#### Classifications of Transmission Media
- Transmission medium
	- Physical path
- Guided media
	- Waves guided along a solid medium
		- Copper twosted pair, optical fiber etc..
	- Unguided media
		- Provides means of transmission but does not guide the signals
			- Often just wireless transmission
			- Uses antennas
				- Atmosåhere, outer space

#### Power budget
Decent amount of signal, not too little and not to strong
Calculated amount of loss that a datalink can tolerate and still work fine

#### Modulation
Encoding information
	Altering the characteristics of a wave

#### Digital modulation
Cannot be directly transmitted in the radio mediun
Translates digital signals into (baseband) analog
Changes from 1010110 to a continous signal
![[Pasted image 20220901140140.png]]

#### Analog Modulation
From analog baseband to passband signal so it could be sent by wireless medium
- AM
- FM
- PM
![[Pasted image 20220901140249.png]]

How it works:
![[Pasted image 20220901140329.png]]

#### Mulitplexing
- Capacity of transmission medium usually exceeds capacity required for transmission of a single signal 
- Multiplexing - carrying multiple signals on a shared medium 
	- "Mux" them together at sender and "demux" them apart on recievers end
	- More efficient use of transmission medium 
	- Sharing the medium with minimum or no interference
Different types of multiplexing:
1. Time division multiplexing
	1. A channel gets the whole spectrum for a short while
![[Pasted image 20220901140748.png]]
2. Frequency division multiplexing 
	1. The spectrum is divided into smaller bands
![[Pasted image 20220901140834.png]]

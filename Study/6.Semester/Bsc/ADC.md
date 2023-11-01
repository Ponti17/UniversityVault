# Table of Contents
---
[[ADC#Data Converter Fundamentals|1.0.0 Data Converter Fundamentals]]


	[[ADC#Data Converter Types|1.1.0 Data Converter Types]]

		[[ADC#Nyquist-Rate Converters|1.1.1 Nyquist-Rate Converters]]

		[[ADC#Oversampling Converters|1.1.2 Oversampling Converters]]


	[[ADC#Ideal A/D Converter|1.2.0 Ideal A/D Converter]]

		[[ADC#Quantization Noise|1.2.1 Quantization Noise]]

		[[ADC#Deterministic Approach|1.2.2 Deterministic Approach]]

		[[ADC#Stochastic Approach|1.2.3 Stochastic Approach]]


	[[ADC#Performance Limitations|1.3.0 Performance Limitations]]

		[[ADC#Resolution|1.3.1 Resolution]]

		[[ADC#Offset and Gain Error|1.3.2 Offset and Gain Error]]

		[[ADC#Accuracy and Linearity|1.3.3 Accuracy and Linearity]]
# Data Converter Fundamentals
---
## Data Converter Types
---
### Nyquist-Rate Converters
---
Generates a series of output values in which each value has a one-to-one correspondence with a single input value. Nyquist-Rate Converters are seldom used at the Nyquist rate due to the difficulty of realizing anta-aliasing and reconstruction filters. Nyquist rate converters typically operate at 1.5 to 10 times the Nyquist rate.

### Oversampling Converters
---
Operate much faster than the input signal's Nyquist rate (often 10 to 512 times faster) and increase the output's SNR by filtering out quantization noise that is not in the signal's bandwidth. In A/D converters, the filtering is performed digitally. Oversampling converters often use noise shaping to place much of the quantization noise outside the input signal's bandwidth. 

## Ideal A/D Converter
---
The block diagram representation for an A/D converter is shown below. $B_{out}$ is the digital output word while $V_{in}$ and $V_{ref}$ are analog input and reference signals.
![[Pasted image 20231018084125.png|500]]
We also define $V_{LSB}$ to be the signal change corresponding to a single LSB change. For an A/D converter, the following equation relates these signals
$$ V_{ref} (b_1 2^{-1} + b_2 2^{-2} + \ldots + b_N 2^{-N}) = V_{in} \pm V_x $$
where 
$$ - \frac{1}{2} V_{LSB} \leq V_X \leq \frac{1}{2} V_{LSB} $$
We see now that there is a range of valid input values that produce the same digital output. This signal ambiguity is produces **quantization error**. A transfer curve for 2-bit converter is shown below
![[Pasted image 20231018084648.png|400]]
The transitions along the $V_{in}$ axis are offset by $\frac{1}{2} V_{LSB}$, so that the midpoints of the staircase curve fall precisely on the equivalent D/A transfer curve. We define the transitions voltages at $V_{ij}$, where $ij$ indicates the upper $B_{out}$ value of the transition. For example $V_{01}$ is shown as the voltage (normalized by $V_{ref}$) for the transition from 00 to 01. 

We note that the relation $-(1/2) V_{LSB} \leq V_X \leq (1/2) V_{LSB}$ only holds true if the input signal remains within 1 LSB of the two last transition voltages. For the 2-bit transfer curve shown above, $V_{in}$ should remain less than $7/8 V_{ref}$ and greater than $-1/8 V_{ref}$. Otherwise, the quantizer is said to be *overloaded* since the magnitude of the quantization error would be larger than $V_{LSB}/2$. 

### Quantization Noise
---
Quantization errors occur even in ideal A/D converters. We can model these errors as being equivalent to an additive noise source. Consider the setup shown below
![[Pasted image 20231018091945.png]]
We have 
$$ V_Q = V_1 - V_{in} $$
this can be rearranged to 
$$ V_1 = V_{in} + V_Q $$
This shows that the quantized signal, $V_1$, can be modelled as the input signal, $V_{in}$, plus some additive quantization noise signal, $V_Q$. 

### Deterministic Approach
---
To understand the properties of the quantization noise $V_Q$, we assume the input signal $V_{in}$ is a ramp. Such an input signal results in the output from the D/A appearing as a staircase, assuming no overloading occurs. Taking the difference between these two signals yields the noise $V_Q$.
![[Pasted image 20231018100121.png]]
We see that the quantization signal, $V_Q$, is limited to $\pm V_{LSB}/2$ and will be so limited for all input signals. The average of $V_Q$ is zero. The RMS value of the noise signal is given by
$$ V_{q(rms)} = \left[ \frac{1}{T} \int_{-T/2}^{T/2} V^2_Q dt \right]^{1/2} = \left[ \frac{1}{T} \int_{-T/2}^{T/2} V^2_{LSB} \left( \frac{-t}{T} \right)^2 dt \right]^{1/2} = \frac{V_{LSB}}{\sqrt{12}} $$
We see that the rms power of the quantization noise is proportional to the size of $V_{LSB}$, which is determined by the number of bits, N, in the converter.

### Stochastic Approach
---
In a more general input case, a stochastic approach is used We assume that the input signal is varying rapidly, such that the quantization error signal, $V_Q$, is a random variable uniformly distributed between $\pm V_{LSB} /2$. The probability density function for such an error signal $f_Q(x)$, will be a constant value.
![[Pasted image 20231018105819.png]]
We recall that the size of $V_{LSB}$ is halved for each additional bit and assuming that $V_{ref}$ remains constant, we see from
$$ V_{Q(rms)} = \frac{V_{LSB}}{\sqrt{12}} $$
that the noise power decreases by 6dB for each additional bit in the A/D converter. Thus for a given input signal waveform, a formula can be derived giving the best possible SNR for a given number of bits in an ideal A/D converter.

Assuming $V_{in}$ is a sawtooth of height $V_{ref}$ (or a random signal uniformly distributed between 0 and $V_{ref}$) and considering only the ac power of the signal, the signal-to-quantization noise ratio (SQNR) is
$$ \textrm{SQNR} = 20 \log \left( \frac{V_{in(rms)}}{V_{Q(rms)}} \right) = 20 \log \left( \frac{V_{ref}/\sqrt{12}}{V_{LSB}/\sqrt{12}} \right) = 20 \log(2^N) = 6.02N \, dB $$
This represents the BEST possible SNR achievable for a data converter with N-bits of resolution since only the quantization noise of an ideal converter is considered.

A more common SNR formula is to assume $V_{in}$ is a sinusoidal waveform between 0 and $V_{ref}$. Thus, the ac power of the sinusoidal wave is $V_{ref}/(2\sqrt{2})$, which results in
$$ SQNR = 20 \log \left( \frac{V_{ref}/(2\sqrt{2})}{V_{LSB} / (\sqrt{12})} \right)  = 6.02N + 1.76 \, dB$$
We see that a sinusoidal signal has 1.76dB more ac power than a random signal uniformly distributed between the same peak levels. We note that this formula gives the best possible SNR for an N-bit A/D converter. The idealized SNR decreases from this value for reduced input signal levels. The plot below shows the idealized SNR for a 10-bit A/D converter versus the sinusoidal input amplitude. We note that these SNR values can be improved by oversampling. 
![[Pasted image 20231018112321.png]]

## Performance Limitations
---
Here we will define some commonly used terms describing the performance of data converters. The transfer response of a D/A converter is defined to be the analog levels that occur for each of the digital input words. Similarly the transfer response of an A/D converter can be defined as the mid-points of the quantization intervals for each of the digital output words. However, since transitions are easier to measure than midpoint values, A/D converter errors are often measured in terms of the analog transition point values, $V_{ij}$.

### Resolution
---
The *resolution* of a converter is defined to be the number of distinct analog levels corresponding to the different digital words. An N-bit resolution implies that the converter can resolve $2^N$ distinct analog levels. Resolution is not an indicator of accuracy, but usually refers to the number of digital input or output bits.

### Offset and Gain Error
---
For an A/D converter the offset error is defined as the deviation of $V_{0\ldots 01}$ from $1/2$ LSB, or mathematically
$$ E_{off(A/D)} = \frac{V_{0\ldots 01}}{V_{LSB}} - \frac{1}{2} \textrm{LSB} $$
The gain error is the difference at the full-scale value between the ideal and actual curves when the offset error has been reduced to zero. For an A/D converter, the equivalent gain error, $E_{gain(A/D)}$ (in units of LSBs) is given by
$$ E_{gain(A/D)} = \left( \frac{V_{1\ldots 1}}{V_{LSB}} - \frac{V_{0 \ldots 01}}{V_{LSB}} \right) - (2^N - 2) $$
Offset and gain error for a 2-bit D/A converter is illustrated below
![[Pasted image 20231018162924.png|400]]

### Accuracy and Linearity
---
The *absolute accuracy* of a converter is defined to be the difference between the expected and actual transfer responses. The absolute accuracy includes the offset, gain and linearity errors. 

The term *relative accuracy* is the accuracy after the offset and gain errors have been removed. It is also known as the *maximum integral nonlinearity error*. 

Accuracy can be expressed as a percentage error of full-scale value, as the effective number of bits, or as a fraction of an LSB. For example, 12-bit accuracy implies that the converter's error is less than the full-scale value divided by $2^{12}$. 

**Integral Nonlinearity (INL) Error**
After both the offset and gain errors have been removed, the integral nonlinearity (INL) error is the deviation of a converters input-output relationship away from the ideal, or least-squares fit, linear relationship.

It is possible to use the endpoints of the converters transfer response to define the straight line. An alternative is to find the best-fit straight line such that the maximum difference is minimized. 

INL values can be defined for each digital word, or the term INL can be defined as the maximum magnitude of the INL values. Typically INL is measured by slowly sweeping the converter input i.e. it is a measure of the converters accuracy at low frequencies.
![[Pasted image 20231019111019.png|500]]

**Differential Nonlinearity (DNL) Error**
In an ideal converter, each analog step size if equal to 1 LSB. In a D/A converter, each output level is 1 LSB from adjacent levels, whereas in an A/D, the transition values are precisely 1 LSB apart. Differential nonlinearity (DNL) is defined as the variation in analog step sizes away from 1 LSB. (Once gain and offset errors are removed). An ideal converter has its maximum DNL of 0 for all digital values, whereas a converter with a DNL of 0.5 LSB has its step sizes varying from 0.5 LSB to 1.5 LSB. 

**Monotonicity (D/A)**
A monotonic D/A converter is one in which the output always increases as the input increases. The slope of the D/A converters transfer response is of only one sign. IF the maximum DNL error is less than 1 LSB, then a D/A converter is always monotonic. Many monotonic converters may, however, have a max DNL greater than 1 LSB. A converter is also monotonic if the max INL is less than 0.5 LSB.

**Missing Codes (A/D)**
An A/D converter does not have any missing codes if the maximum DNL is less than 1 LSB or if the maximum INL is less than 0.5 LSB.

**A/D Conversion Time and Sampling Rate**
The conversion time is the time taken for the converter to complete a single measurement including acquisition time of the input signal. The maximum sampling rate is the speed at which samples can be continuously converted and is typically the inverse of the conversion time. 

Some converters have a large latency between the input and the output due to pipelining or multiplexing, yet still maintain a high SR. 

**Sampling-Time Uncertainty**
Converters have limited accuracy when their sampling instances are ill defined. To quantify this sampling time uncertainty (aka aperture jitter), for sinusoidal waveforms, consider a full-scale signal, $V_{in}$, applied to an N-bi, signed, A/D converter with frequency $f_{in}$
$$ V_{in} = \frac{V_{ref}}{2} \sin(2 \pi f_{in} t)$$
The slope of $V_{in}$ at the peak is small, sampling time uncertainty is less of a problem near peak values. The maximum rate of change occurs at the zero crossing
$$ \frac{\Delta V}{\Delta t} \Biggl|_{max} = \pi f_{in} V_{ref} $$
If $\Delta t$ represent sampling time uncertainty, and we want to keep $\Delta V$ less than $1 V_{LSB}$ 
$$ \Delta t < \frac{V_{LSB}}{\pi f_{in} V_{ref}} = \frac{1}{2^N \pi f_{in}} $$
For example, an 8-bit converter sampling a full-scale 250 MHz sinusoidal signal must keep its sampling-time uncertainty under 5 ps to maintain 8-bit accuracy. 

**Dynamic Range**
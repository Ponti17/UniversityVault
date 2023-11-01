# Table of Contents
---
[[SAR_Converters#Successive-Approximation Converters|1.0.0 Successive-Approximation Converters]]

	[[SAR_Converters#D/A-Based Successive Approximation|1.1.0 D/A-Based Successive Approximation]]
# Successive-Approximation Converters
---
Successive-Approximation (SA) A/D converters are simple, relative quick and can provide good resolution. 

**Binary Search**
The basic operation of SA converters can be compared to a search algorithm called binary search. 

Consider a game of guessing a random number from 1 to 128. The first question might be "Is the number greater than 64"? If yes, then the next question might be "Is the number greater than 96". Every question essentially divided the search space in two.

In general, the desired can be found in $N$ steps for a set of organized data of size $2^N$. 

**Flow Graph**
![[Pasted image 20231021122820.png|500]]

SA converters apply a binary search algorithm to determine the closest digital word to match an input signal. In the first period, the MSB, $b_1$, is determined. In the second period, the next bit, $b_2$, is determined, followed by $b_3$ and so on. In its most basic implementation, a SA converter requires N clock cycles to complete a N-bit conversion. 

## D/A-Based Successive Approximation
---
![[Pasted image 20231021123144.png]]
The successive-approximation register (SAR) and control logic are entirely digital and perform the necessary binary search. At the end of the conversion, the digital value in the SAR results in the voltage $V_{D/A}$ being within $0.5 V_{LSB}$ of the input signal. Typically the D/A converter determines the accuracy and speed of the A/D converter. A sample and hold is required at the input so that the value to be converted does not change during the conversion time.


For a Binary Symmetric Channel (BSC), with inputs 0,1. There is a probability P (error) that a 0 will be interpreted as a 1.
![[bsc.png]]
The channel capacity $C$ is the max rate of perfect transmission. the capacity for a BSC
$$ C_{BSC} = p\,log_2p + (1 - p)\log_2(1 - p) \,\textrm{bits/timeslot} $$
The expression is plotted below
![[Pasted image 20230621084027.png]]
Datawords for data before going into the channel and codewords for what we are going to code the data into when sending into the channel. For the datawords
$$ 00, \hspace{20pt} 01, \hspace{20pt} 10, \hspace{20pt} 11 $$
the minimum distance MD is 1. If a error happened in one of them it would look like another. If we use parity checks and add a third bit that always make an even amount of 1's
![[Pasted image 20230621084712.png]]
we now need to use the channel 3 times to send 2 bits. So the rate
$$ R = 2/3 $$
Now 2 bits must be changed for a codeword to look like another. So the minimum distance MD = 2. For an arbitrary encoding
![[Pasted image 20230621085213.png]]
If an error is detected and the received codeword does not match, we can now look at which CW it resembles most, and correct the error.

## AWGN Channel
---
For a Additive White Gaussian Noise (AWGN) channel we take datawords of length N and convert it into codewords of length M.
![[Pasted image 20230621085626.png]]
For $N,M \to \infty$, the capacity
$$ C = W \log_2 \left( 1 + \frac{P_{ave}}{WN_0} \right)\, \textrm{bits/second} $$
It is obviously a problem that the block words must be infinite. In practice codewords can be chosen such that we approach the channel capacity given above.
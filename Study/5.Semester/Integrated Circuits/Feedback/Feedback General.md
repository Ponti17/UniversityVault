# Feedback General
---
A negative feedback system is shown below
![[Pasted image 20231127122827.png|400]]
Where $H(s)$ and $G(s)$ is called the feedforward and the feedback networks, respectively. The input to $H(s)$ is called the feedback error. The output
$$ Y(s) = H(s)[X(s) - G(s)Y(s)] $$
So the transfer function
$$ \frac{Y(s)}{X(s)} = \frac{H(s)}{1 + G(s)H(s)} $$
We call $H(s)$ the *open-loop* transfer function and $Y(s)/X(s)$ the *closed-loop* transfer function. In most cases $H(s)$ represents an amplifier and $G(s)$ is a frequency-independent quantity.  The input of $H(s)$ is a virtual ground because the signal amplitude at this point is small. We sometimes replace $G(s)$ by a frequency-independent quantity $\beta$. 

## Properties of Feedback Circuits
---
Negative feedback yields a variety of useful benefits.

### Gain Desensitization
---
Consider the common-source stage (a)
![[Pasted image 20231127123532.png|500]]
The voltage gain is equal the intrinsic gain $g_m r_O$. Both of these parameters vary greatly with process and temperature. We now configure the circuit as shown in (b). The voltage gain at frequencies low enough that $C_2$ draws a negligible current
$$ \frac{V_{out}}{V_{in}} = \frac{1}{\left(1 + \frac{1}{g_m r_O} \right) \frac{C_2}{C_1} + \frac{1}{g_m R_O}} $$
If $g_m R_O$ is large enough, the terms in the denominator can be neglected yielding
$$ \frac{V_{out}}{V_{in}} = \frac{C_1}{C_2} $$
This example reveals that the closed-loop gain is less sensitive to device parameters than the open-loop gain is. Gain desensitization can be quantified by
$$ \frac{Y}{X} = \frac{A}{1 + \beta A} \approx \frac{1}{\beta} \left( 1 - \frac{1}{\beta A} \right) $$
Where $\beta A \gg 1$. This quantity $\beta A$ is called the loop gain. The higher the loop gain the less sensitive $Y/X$ will be to variations in $A$, i.e. the accuracy of the closed-loop gain improves by maximizing $\beta A$. 

**Loop Gain**
To calculate the loop gain, we set the input to (ac) zero, break the loop at some point and inject a test signal in the right direction. We then follow the signal around the loop, and obtain the value that returns to the break point. The negative of the transfer function thus derived is the loop gain. 
![[Pasted image 20231127132614.png|400]]
for the system above, we have
$$ V_t \beta(-1) A = V_F $$
and hence
$$ V_F/V_t = -\beta A $$
![[Pasted image 20231127132931.png|400]]
For the common-source circuit circuit we write
$$ V_X = V_t \frac{C_2}{C_1 + C_2} $$
and
$$ V_t \frac{C_2}{C_1 + C_2} (-g_m r_O) = V_F $$
That is
$$ \frac{V_F}{V_t} = - \frac{C_2}{C_1 + C_2} g_m r_O $$
The current drawn by $C_2$ from the output is neglected.

### Terminal Impedance Modification
---
![[Pasted image 20231127133428.png]]
A capacitive voltage divider senses the output voltage of a common-gate stage, applying the result to the gate of current source $M_2$ and hence returning a signal to the input. Neglecting channel-length modulation and the current drawn by $C_1$, we break the feedback loop as shown in (b) and write
$$ R_{in,open} = \frac{1}{g_{m1} + g_{mb1}} $$
For the closed-loop circuit (c) we write
$$ V_{out} = (g_{m1} + g_{mb1})V_X R_D $$
$$ V_P = V_{out} \frac{C_1}{C_1 + C_2} = (g_{m1} + g_{mb1})V_X R_D \frac{C_1}{C_1 + C_2} $$
The small-signal drain current of $M_2$ equals $g_{m2}(g_{m1} + g_{mb1})V_X R_D C_1/(C_1 + C_2)$. We can now determine $I_X$
$$ I_X = (g_{m1} + g_{mb1}) \left( 1 + g_{m2} R_D \frac{C_1}{C_1 +C_2} \right) $$
The input impedance
$$ $R_{in,closed} = V_X/I_X = \frac{1}{g_{m1} + g_{mb1}} \frac{1}{1 + g_{m2}R_D \frac{C_1}{C_1 + C_2}} $$
We see that the feedback network reduced the input resistance by a factor
$$ \frac{1}{1 + g_{m2}R_D} \frac{C_1}{C_1 + C_2} $$
which is the loop gain. In the same way the output resistance is also reduced.

### Bandwidth Modification
---
We start by assuming that a feedforward amplifier has a one-pole transfer function
$$ A(s) = \frac{A_0}{1 + \frac{s}{\omega_0}} $$
Where $A_0$ denotes the low-frequency gain and $\omega_0$ is the 3-dB bandwidth. The transfer function of the closed-loop system
$$ \frac{Y}{X}(s) = \frac{ \frac{A_0}{1 + \frac{s}{\omega_0}} }{1 + \beta \frac{A_0}{1 + \frac{s}{\omega_0}}} = \frac{A_0}{1 + \beta A_0 + \frac{s}{\omega_0}} = \frac{ \frac{A_0}{1 + \beta A_0} }{1 + \frac{s}{(1 + \beta A_0)\omega_0}} $$
	The numerator is simply the closed-loop gain at low frequencies. The denominator reveals a pole at $(1 + \beta A_0)\omega_0$. Thus, the 3-dB bandwidth has increased by a factor of $1 + \beta A_0$, albeit at the cost of a proportional reduction in the gain. 

### Nonlinearity Reduction
---
Down below the input-output characteristic of an amplifier with/without feedback is shown
![[Pasted image 20231127143515.png]]

## Types of Amplifiers
---
There are four types of amplifiers.
![[Pasted image 20231127143713.png]]
Circuits sensing a voltage must exhibit at high input impedance, whereas those sensing a current must provide a low input impedance. Circuits generating a voltage must exhibit a low output impedance while those generating a current must provide a high output impedance.
![[Pasted image 20231127143931.png]]

## Sense and Return Mechanisms
---
A feedback loop requires sensing the output signal and returning a fraction of the result to the summing node a the input. With voltage or current quantities as input and output signals, there are four types of feedback: 
**voltage-voltage, voltage-current, current-current, current-voltage**.
where the first entry is the quantity sensed at the output and the second the type of signal returned to the input. 

To sense a voltage we place a voltmeter in parallel to the port. When used in a feedback system, this type of sensing is called shunt feedback.

To sense a current, a current meter is inserted in series with the signal. Also called series feedback. In practice, a small resistor replaces the current meter, with the voltage drop across the resistor serving as a measure of output current.
![[Pasted image 20231127145339.png]]
**NOTE**: For voltage subtraction, the input and feedback signals are applied to two distinct nodes. For current feedback they are applied to a single node.



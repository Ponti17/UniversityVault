# Table of Contents
---
[[Smith Chart Matching#Smith Chart Matching|1.0.0 Smith Chart Matching]]

	[[Smith Chart Matching#Series and Parallel Components|1.1.0 Series and Parallel Components]]
		[[Smith Chart Matching#Series Components|1.1.1 Series Components]]
		[[Smith Chart Matching#Parallel Components|1.1.2 Parallel Components]]

	[[Smith Chart Matching#Impedance Matching|1.2.0 Impedance Matching]]
		[[Smith Chart Matching#Example|1.2.1 Example]]

	[[Smith Chart Matching#Stub Line Design|1.3.0 Stub Line Design]]
		[[Smith Chart Matching#Example|1.3.1 Example]]

	[[Smith Chart Matching#Line Matching|1.4.0 Line Matching]]
# Smith Chart Matching
---
The following include notes for impedance matching with the Smith Chart.

## Series and Parallel Components
---
The addition of series or parallel resistors, capacitors or inductors allows us to move around on the Smith chart.
### Series Components
---
When placing series components you move on the red impedance lines and circles.

**Series Capacitor**
The real part stays the same, the imaginary part decreases.

**Series Inductor**
The real part stays the same, the imaginary part increases.

**Series Resistor**
The real part increases, the imaginary part stays the same.
![[Pasted image 20231016212014.png|500]]

### Parallel Components
---
**Parallel Capacitor**
The real part stays the same, the imaginary part increases.

**Parallel Inductor**
The real part stays the same, the imaginary part decreases.

**Parallel Resistor**
The real part decreases. The imaginary part stays the same.
![[Pasted image 20231016212358.png|500]]

## Impedance Matching
---
We have a load impedance $Z_{L}$ with an arbitrary value. We have to hook up the load impedance to a network with a load impedance $Z_{in}$ (usually 50 ohm).
![[Pasted image 20231023115504.png|400]]

For an arbitrary impedance placed on the Smith chart we can move around using either series/parallel components as described above or by inserting a transmission line
![[Pasted image 20231023120039.png|300]]
The goal of impedance matching is to move the impedance to the center point.
### Example
---
Find a matching network to match $Z_L = 100 + 100j$ to $Z_{in} = 50$. Assume a line impedance of $Z_0 = 50$. 

We normalize the load impedance
$$ Z_L' = 2 + 2j $$
We want to match this to the normalized input impedance
$$ Z_{in}' = 1 $$
The point on the Smith chart and a possible path to the center
![[Pasted image 20231023170533.png|500]]
First we use a shunt inductor to move on a blue circle. Second we use a series capacitor to move on a red circle down to the center. We now must determine the values of the inductor and the capacitor. The point after the shunt inductor can be read to be
$$ Z_X' = 1 + 1.7j $$
The admittance is then
$$ Y_X' = 1/Z_X' = 0.25 - 0.44j $$
The load admittance
$$ Y_L' = 0.25 - 0.25j $$
We see that our inductor has to add $-0.19j$ admittance or
$$ Z_L' = 5.26j $$
of impedance (normalized). We are now at the point $Z_X' = 1 + 1.7j$. We need to remove $1.7j$ of impedance to land $Z' = 1$. Meaning that the capacitors impedance
$$ Z_C' = -1.7j $$
We now denormalize the values
$$ Z_L = 263j, \hspace{20pt} Z_C = -85j $$ 
## Stub Line Design
---
An open stub with length $l$ acts as a capacitor. 
A closed stub acts as an inductor.
![[Pasted image 20231023173148.png]]
Lets say we want to model a capacitor with $-20j$ impedance normalized to $Z_C' = -0.4j$. From the right of the Smith chart we move to the imaginary impedance -0.4j, and read the wavelength. 
![[Pasted image 20231023173434.png|500]]
We read $0.43\lambda$. We subtract the starting point and get
$$ l = 0.439\lambda - 0.25\lambda = 0.189\lambda $$
### Example
---
Consider the circuit
![[Pasted image 20231026104946.png|400]]
We want to determine the input impedance $Z_{in}$. For a load impedance of
$$ Z_L = 30 - 25j $$
We normalize
$$ Z_L' = 0.6 - 0.5j $$
We know that inserting a series line rotates the point on a red circle. Since it is $\lambda/4$ it is a half circle.
![[Pasted image 20231026105529.png|300]]
We land at $0.98 + 0.82j$. Since the stub is open we start at the middle right of the smith chart ($0.25\lambda$) and rotate $0.15\lambda$ clockwise. We read off the chart that the stub has impedance $Z_{stub}'' = -0.73j$. We convert to admittance
$$ Y_{stub}' = 1.38j $$
We now add the admittance to the point
$$ Y_{in}' = 0.6 + 0.87j $$
The input impedance
$$ Z_{in}' = 0.54 - 0.78j $$
Denormalized
$$ Z{in} = 27 - 39j $$
## Line Matching
---
A typical matching network for an arbitrary $Z_L$
![[Pasted image 20231026110619.png|400]]
![[Pasted image 20231026110632.png|500]]

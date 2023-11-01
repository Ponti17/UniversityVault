### Basics
---
The Smith chart arranges the complex $\Gamma$ plane into a grid of circles, which can be identified as the normalized load impedances $Z_L/Z_0$. 
![[loadedtrans.png]]
The Smith is used for calculating the relationship between the load impedance and the reflection coefficient.
$$\Gamma = \frac{Z_L - Z_0}{Z_L + Z_0}$$
We start by normalizing the load impedance (the normalized impedance is without unit)
$$ Z_{norm} = Z_L' = \frac{Z_L}{Z_0} $$
The reflection coefficient of the normalized load impedance
$$ \Gamma = \frac{Z_L' - 1}{Z_L' + 1} $$
The smith chart is a graphical tool for solving the equation above. The value $Z_L'$ is complex valued where the real part must be larger than 0. The reflection coefficient has magnitude $|\Gamma| \leq 1$, since if it is larger than 1 the reflected wave would be larger than the incident wave. 

The smith chart maps all possible $Z_L'$ values to $\Gamma$ values.
![[etmmap.png]]
A line drawn in the impedance $Z_L'$ plane with constant Re equals a circle in the smith chart. A line drawn in the impedance plane with constant Im equls a curved line in the smith chart.
![[asitjha.png]]
It is now possible to easily identify Gamma values for a specific load impedance. E.g. $Z_L' = 2 + 1j$. We find the circle Re = 2, and the curved line Im = 1j. The gamma value is then the magnitude of the vector going from origo to that point.
![[Pasted image 20231015230222.png|600]]

### Line Transformation
---
The Smith chart can be used to derive the input impedance of a line load combo:
![[Pasted image 20231016171206.png]]
There is a phase delay between $U_1^+$ and $U_2^+$ by the length of the line $\beta l$. So
$$ U_1^- = U_2^- e^{-j \beta l}, \hspace{20pt} U_1^+ = U_2^+ e^{j\beta l} $$
The reflection coefficient
$$ \Gamma_1 = \frac{U_1^-}{U_1^+} = \Gamma_2 e^{-2j \beta l} $$
So the difference between $\Gamma_1$ and $\Gamma_2$ is simply a angle difference of $2 j \beta l$ i.e. a rotation in the smith chart.
![[Pasted image 20231016171922.png|400]]
Consider the example below
![[Pasted image 20231016172624.png]]
Since the transmission line is $0.3\lambda$, there is a phase difference in one direction 
$$ \textrm{phase delay} = 0.3 * 360^{\circ} = 108^{\circ} $$
Since the wave travels forth and then back, we have to add $216^{\circ}$. 
![[Pasted image 20231016172809.png|500]]
We see that the normalized input impedance is $Z_{in}' = 0.39 - 1.09j$. 

The distance $\lambda$ to generator equals a rotation on the smith chart. We see that the first impedance is at $0.062\lambda$, the second impedance is therefore at $0.062\lambda + 0.3\lambda = 0.362\lambda$.

### From Z to Y
---
The impedance $Z$ can be obtained from the admittance $Y$ (and vice versa).
$$ Z = \frac{1}{Y} $$
The reflection coefficients
$$ \Gamma = \frac{Z - 1}{Z + 1} = \frac{\frac{1}{Y} - 1}{\frac{1}{Y} + 1} = - \frac{Y - 1}{Y + 1} $$
Or
$$ -\Gamma = \frac{Y - 1}{Y + 1} $$
The admittance can be found by mirroring Z by the origin.
![[Pasted image 20231016174033.png|500]]

### Example
---
![[Pasted image 20231016180720.png]]
The first step is to normalize impedance values.
![[Pasted image 20231016180802.png]]
We place the point $Z_L = 2 -0.5j$ on the smith chart. 

To determine $Z_2$ with the series capacitor, we add the capacitors impedance i.e. $Z_2 = 2 - 1j$. 

To determine $Z_3$, we do a rotation equal to $0.3\lambda$ or $0.3 * 360^{\circ} = 108^{\circ}$. We land at $Z_3 = 0.50 + 0.49j$. 

The impedance $Z_4$ is parallel to $Z_3$. To determine $Z_4$, we convert $Z_3$ to admittance by reading off the blue grid. We get $Y_3 = 1 - 1.01j$. The admittance of the inductor $Y_{ind} = 1 / 1j = -1j$. We now add the two admittances $Y_4 = 1 - 2j$. The impedance is then $Z_4 = 1 / Y_4 = 0.2 + 0.4j$. 
![[Pasted image 20231016211246.png|500]]
Finally we multiply $Z_4$ with $Z_0$ to get the final input impedance $Z_4 = 10 + 20j$. 

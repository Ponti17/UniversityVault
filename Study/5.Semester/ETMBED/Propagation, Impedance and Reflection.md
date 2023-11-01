Voltages and currents travel as waves on a transmission line. The characteristics of these travelling waves are governed by the complex propagation constant $\gamma$. 

The constant $\gamma$ is related to the elementary constants of the transmission line.
$$ \gamma = \sqrt{(R + j\omega L)(G + j\omega C)} $$
where R, L, G and C are the elementary constants of the transmission line. And $\omega$ is the angular frequency. The constant $\gamma$ can be written in complex form
$$ \gamma = \alpha + j \beta $$
The travelling wave in the forward direction is given by
$$ V^+ e^{\gamma x} = V^+ e^{-(\alpha + j \beta)x} = |V^+| e^{-\alpha x} e^{-j \beta x}$$
So the travelling wave has an amplitude given by the norm of $V^+$ and $e^{-\alpha x}$ and a phase $e^{-j\beta x}$.

Beta represents the phase change per unit length (rad/m).  The phase change is related to the wavelength.
$$ \beta = \frac{2\pi}{\lambda} $$
The other constant $\alpha$ (attenuation constant) represents how a wave loses its amplitude exponentially by $e^{-\alpha x}$.  $\alpha$ has unit neper/meter. If $\alpha = 1$ neper/m, then the amplitude will be reduced to $|V^+| \frac{1}{e}$ after 1 meter. The effective travel distance of the transmission line is 
$$ \textrm{Effective travel distance} =  \frac{1}{\alpha} $$
The attenuation is often expressed in dB
$$ dB \to - 20 \log(e^{-\alpha x}) $$
### Transmission Line Example
---
Consider the following parameters. Resistance, inductance, capacitance, conductance and frequency:
$$ R = 0.5 \Omega/m, \hspace{10pt} L = 0.2 \mu/m, \hspace{10pt} C = 100 pF/m, \hspace{10pt} G = 0.1 V/m, \hspace{10pt} f = 1 GHz $$
First we convert the frequency into the angular frequency
$$ \omega = 10^9 * 2\pi \, rad/s $$
The propagation constant
$$ \gamma = \sqrt{ (0.5 + 10^{-6} *0.2j\omega)(0.1 + j\omega 100 * 10^{-12}) } $$
Separating real and imaginary parts
$$ \gamma = 2.23 + j28.2 $$
We see that
$$ \alpha = 2.23 \, Nepers/m, \hspace{20pt} \beta = 28.2 \, rad/m $$
At some point $x = 0, t = 0$ the voltage was measured. And we would like to know the voltage at some other point and time. 

Lets consider a measured voltage of $8.66V$ at $x = 0, t = 0$. We would like to know the voltage at $x = 1m, t = 100ns$. We are interested in both the voltage and the peak voltage at that location. The voltage as a function of time
$$ V(t) = Re\{ V^+ e^{-\alpha x} e^{-j\beta x + j\omega t} \} $$
The quantity $V^+$ is in general a complex quantity, since the voltage at $x = 0, t = 0$ may not be at its maximum value. We can write the voltage function as
$$ V(t) = |V^+| \cos(\phi + \omega t - \beta x) e^{-\alpha x} $$
where $\phi$ is the initial phase. If we substitute the values into the expression
$$ 8.66 = |V^+| \cos \phi $$
Since we do not know the initial phase the problem is unsolvable. Lets assume the initial phase was $30^\circ$. So
$$ 8.66 = |V^+| \cos 30^\circ \hspace{20pt} \to \hspace{20pt} |V^+| = 10V $$
We now substitute $|V^+|$ into $V(t)$ to get the voltage at $x = 1m, t = 100ns$. 
$$ V(100ns) = 10 \cos(30^\circ + 10^9 *2\pi *100 * 10^{-9} - 28.2 *1) e^{-2.23 * 1} = -0.89 V $$
The peak voltage at $x=1m$ is
$$ \textrm{Peak voltage} = |V^+| e^{-1\alpha } = 1.75V $$
If a wave is travelling backwards the propagation
$$ |V^+| e^{+\alpha x} e^{+j\beta x + j\omega t} e^{j\phi} $$
The amplitude will now increase from $x=0$ to $x=1m$. 
$$ V(100ns) = Re\{ |V^+| e^{+\alpha x} e^{+j\beta x + j\omega t} e^{j\phi} \}  = -83.77V$$
### Characteristic Impedance
---
The relationship between current and voltage on the forwards and backwards travelling wave
$$ \frac{V^+}{I^+} = \frac{(R + j\omega L)}{\gamma} =\sqrt{ \frac{R+j\omega L}{G + j\omega C} } $$
$$ \frac{V^-}{I^-} = - \frac{(R + j\omega L)}{\gamma} = - \sqrt{ \frac{R + j\omega L}{G + j \omega C} } $$
We see that we now have a new characteristic parameter of the line, since it depends only on line parameters. Since the parameter is a voltage and current ratio, it is an impedance. The quantity is therefore called the characteristic impedance of the line
$$ Z_0 = \sqrt{ \frac{R + j\omega L}{G + j\omega C} } $$
The characteristic impedance and the propagation constant completely characterize the propagation of a transmission line. 

Without any boundary conditions, the forward traveling wave *always* sees an impedance of $Z_0$, while the backwards travelling wave *always* sees an impedance of $-Z_0$. 

The real part of $Z_0$ corresponds to a positive resistance for the forwards travelling wave. The real part of $Z_0$ corresponds to a negative resistance for the backwards travelling wave. This corresponds to a receiving of energy when looking in the positive $x$ direction. The negative resistance is therefore a manifestation of the direction of energy flow.

The voltage on a transmission line can be written as
$$ V = V^+ e^{-\gamma x} + V^- e^{\gamma x} $$
$$ I = \frac{V^+}{Z_0} e^{-\gamma x} - \frac{V^-}{Z_0} e^{\gamma x} $$
### Boundary Conditions
---
![[bou.png]]
Normally there are two special points on a transmission line. One where the generator is connected, and one where the load impedance is connected. 

Either we can define the origin at the generator end or the load end. Generally it is preferred to define the origin at the load end. So we now have a distance $l$ measured from load to generator. We can substitute $x = -l$. 
$$ V = V^+ e^{\gamma l} + V^- e^{-\gamma l} $$
$$ I = \frac{V^+}{Z_0} e^{\gamma l} - \frac{V^-}{Z_0} e^{-\gamma l} $$
We now have a boundary condition that is at $l = 0$, where we have terminated the line into some impedance $Z_L$. At $l = 0$ the impedance must be
$$ Z_L = \frac{V}{I} \Bigl|_{l = 0} = Z_0 \frac{V^+ + V^-}{V^+ - V^-} $$
We now define a new parameter, reflection coefficient
$$ \Gamma(l) =\frac{V^- e^{-\gamma l}}{V^+ e^{\gamma l}} $$
which is the ratio of the voltage of the backwards and forwards voltage. At $l = 0$
$$ \Gamma(0) = \frac{V^-}{V^+} $$
So the load impedance
$$ Z_L = Z_0 \left( \frac{1 + \Gamma(0)}{1 - \Gamma(0)}\right) $$
If full transfer of power to the load, the reflection coefficient should ideally be very low. 













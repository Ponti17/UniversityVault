# Microwave Oscillator Design
---
## Introduction
In a negative resistance oscillator we refer to the matching networks as the terminating and the load (or resonant) networks. The load-matching network determines the frequency of oscillation, and the terminating network is used to provide proper matching.

The condition $|\Gamma_{IN}| > 1$ is necessary for oscillation. 
## Oscillation Conditions
### Feedback Oscillators
The system diagram of a feedback oscillator
![[Pasted image 20231221092954.png|300]]
In many practical oscillators the gain $A_v(j\omega)$ is a real constant $A_{v0}$ at the frequency of oscillation. To reach oscillation the feedback must be positive i.e. a phase shift of $0^{\circ}$ or $360^{\circ}$. For oscillations to occur, an output signal must exist with no input signal applied
$$ \frac{V_o}{V_i} = \frac{A_v(j\omega)}{1 - \beta(j\omega) A_v(j\omega)} $$
with $V_i = 0$ a finite $V_o$ is possible only when the denominator is zero i.e.
$$ 1 - \beta A_v = 0 \hspace{10pt} \Rightarrow \hspace{10pt} \beta(j\omega) A_v(j\omega) = 1$$
the above expression states that for oscillations to occur the loop gain must be unity (Barkhausen criterion). The above expression can be expanded to rectangular form
$$ \beta_r(\omega) A_{vo} + j\beta_i(\omega)A_{vo} = 1 $$
$\Updownarrow$
$$ \beta_r(\omega) A_{vo} = 1 \hspace{10pt} \Rightarrow \hspace{10pt} A_{vo} = \frac{1}{\beta_r(\omega)} $$
$$ \beta_i(\omega) A_{vo} = 0 \hspace{10pt} \Rightarrow \hspace{10pt} \beta_i(\omega) = 0 $$
The first equation is known as the gain condition and the second is known as the frequency of oscillation condition. The second condition gives the frequency at which the phase shift is $0^{\circ}$. 
### One-Port Negative-Resistance Oscillators
![[Pasted image 20231221095638.png|300]]
For the microwave circuit above the closed-loop gain function
$$ a_L = \frac{a_n \Gamma_{in}(j\omega)}{1 - \Gamma_{in}(j\omega)\Gamma_L(j\omega)} $$
where $\Gamma_L$ represent the load reflection coefficient and $\Gamma_{in}$ the input reflection coefficient of an active device. $a_n$ is a small noise voltage. The circuit will oscillate when $1 - \Gamma_{in}\Gamma_L$ has right-half plane zeroes. For oscillations to occur the loop gain must be unity
$$ \Gamma_{in}(j\omega) \Gamma_L(j\omega) = 1 $$
The input impedance of the active device $Z_{in}$ is in general a function of the voltage amplitude and frequency. For oscillations to occur the real part of $Z_{in}$ must be negative. 
The general schematic for a one-port negative-resistance oscillator is shown below
![[Pasted image 20231221094639.png|300]]
The device is represented by the amplitude and frequency-dependent impedance
$$ Z_{in}(A,\omega) = R_{in}(A,\omega) + j X_{in}(A,\omega) $$
Where $A$ is the amplitude of $i(t)$ and
$$ R_{in}(A,\omega) < 0 $$
The oscillator is constructed by connecting it to a passive load impedance
$$ Z_L(\omega) = R_L(\omega) + jX_L(\omega) $$
The network oscillated at amplitude $A = A_0$ and frequency $\omega = \omega_0$ when
$$ \Gamma_{in}(A_0, \omega_0) \Gamma_L(\omega_0) = 1 $$
Since 
$$ \Gamma = \frac{Z - Z_0}{Z + Z_0} $$
we can express the loop-gain criterion
$$ Z_{in}(A_0, \omega_0) + Z_l(\omega_0) = 0 $$
$\Updownarrow$
$$ R_{in}(A_0, \omega_0) + R_L (\omega_0) = 0, \hspace{10pt} X_{in}(A_0, \omega_0) + X_l(\omega_0) = 0 $$
The device is unstable over some frequency range $\omega_1 < \omega < \omega_2$ if $R_{in} < 0$. That is
$$ |R_{in}| > R_L $$
The oscillations will continue to build up as long as the loop resistance is negative. The amplitude of the current must eventually reach a steady state value $A = A_0$ and $\omega = \omega_0$ which occurs when the loop resistance is zero.
### Two-Port Negative-Resistance Oscillators
The block diagram for a two-port oscillator is shown below.
![[Pasted image 20231221113133.png|400]]
The transistor network is characterized by its S-parameters. $Z_T$ is the terminating network impedance and $Z_L$ is the load impedance. We see that in an oscillator either port of the transistor can be used as the terminating port. 

When the two-port network is potentially unstable, an appropriate $Z_T$ permits the two-port to be represented as a one-port negative-resistance device with input impedance $Z_{in}$. The conditions for a stable oscillation are given by (5.2.16),(5.2.17),(5.2.20):
$$  R_{in}(A_0, \omega_0) + R_L (\omega_0) = 0, \hspace{10pt} X_{in}(A_0, \omega_0) + X_l(\omega_0) = 0 $$
To start the oscillation, the value of $R_L$ is selected according to (5.2.22) 
$$ R_L = |R_{in}(0,\omega)|/3 $$
When the input is made to oscillate, the terminating port also oscillates. The input port is oscillating when
$$ \Gamma_{in}\Gamma_L = 1 $$
From (5.3.2) (5.3.3)
$$ \Gamma_T = \frac{1 - S_{11}\Gamma_L}{S_{22} - \Delta \Gamma_L} $$
$$ \Gamma_{out} = \frac{S_{22} - \Delta \Gamma_L}{1 - S_{11}\Gamma_L} $$
We see that
$$ \Gamma_{out} \Gamma_T = 1 $$
A simple design procedure
- Use a potentially unstable transistor at $\omega_0$
- Design the terminating network to make $|\Gamma_{in}| > 1$ (series or shunt feedback)
- Design the load network to resonate $Z_{in}$ and let
$$ X_L(\omega_0) = -X_{in}(\omega_0), \hspace{10pt} R_L = R_0/3 $$




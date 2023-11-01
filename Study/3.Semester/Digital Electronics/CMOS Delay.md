# CMOS Delay
---
Because a transistor gate is an insulator, it can be modelled as a capacitor
![[mos_cap.png|500]]

When a transistor is turned on some current $I_{ds}$ flows between source and drain. The capacitance IV equation
$$ I = C \frac{dV}{dt} $$
For switching between 0 and $V_{DD}$ 
$$ \Delta t = \frac{C}{I} V_{DD} $$
The delay of a logic gate is determined by the current it can deliver and the capacitance it is driving. So to calculate dela wee need
- Load capacitance
- Drive current
both of which are proportional to transistor size.

## Parasitic Capacitance
---
Each terminal of a MOS transistor has capacitance. The gate capacitance $C_g$:
$$ C_g = C_{ox}WL = \frac{\varepsilon_{ox}}{t_{ox}} WL $$
For a MOS transistor there are the following capacitances
- Diffusion capacitances of source and drain ($C_{sb}$ and $C_{db}$)
- Overlap capacitances of source and drain ($C_{gs}$ and $C_{gd}$)
![[mos_cap2.png]]

## Delays
---
- Propegation delay time ($t_{pd}$): Maximum time difference between the time input crossing 50% to the time output crossing 50%. $t_{pd} = \textrm{Max}(t_{pdr}, t_{pdf})$.
- Contamination delay time ($t_{cd}$): Minimum time from the input crossing 50% to the output crossing 50%. $t_{cd} = \textrm{Min}(t_{pdr}, t_{pdf})$.
- Rise time ($t_r$): Time for a waveform to rise from 20% to 80% of its steady-state value.
- Fall time ($t_f$): Time for a waveform to fall from 80% to 20% of its steady-state value.
- Edge rate ($tr_{rd}$): $t_{rf} = (t_r + t_f)/2$.
![[delay.png|500]]

## Transient Response
---
The best way to compute delay is the develop
$$ \frac{dV_{out}}{dt} f(V_{in}, I, C) $$
The solution of the differential equation is called the **transient response**. The delay is the time when the output reaches $V_{DD}/2$. In circuits the differential equation is based on charging or discharging of parasitic capacitance.
$$ I = C \frac{dV}{dt} $$
In an integrated circuit, the node capacitances consists of
$$ C_{node} = C_{gate\_load} + C_{diffusion\_drivers} + C_{wires} $$
In this course we ignore $C_{wires}$.

## Example
---
An inverter $X_1$ drives another inverter $X_2$. Suppose a voltage step from 0 to $V_{DD}$ is applied to node A and we wish to compute the delay of $X_1$ ($t_{pdf}$).
![[inv_Delay.png]]
![[inv_dela2.png]]
The IV equation of a capacitor
$$  I = C \frac{dV}{dt} $$
We simply the capacitance  at node B
$$ I_{ds,N1} = -C_B \frac{dV_b}{dt} $$
The drain-source current at saturation
$$ I_{ds,N1} = \beta \frac{(V_{DD} - V_t)^2}{2} $$
The drain-source current in linear region
$$ I_{ds, N1} = \beta \left( V_{DD} - V_t - \frac{V_B}{2} \right)V_B $$
Using these equations we get
$$ \frac{dV_B}{dt} = - \frac{\beta}{C_B} \frac{(V_{DD} - V_t)^2}{2} $$
at saturation. And
$$  \frac{dV_B}{dt} = - \frac{\beta}{C_B}  \left( V_{DD} - V_t - \frac{V_B}{2} \right)V_B $$
We use the following long channel model parameters
- $L = 50 nm$
- $V_{DD} = 1.0 V$
- $V_{t\_n} = V_{t\_p} = 0.3V$
- $t_{ox} = 10.5 Å$
- $\mu_n = 2\mu_p = 80 cm^2/Vs$
The widths of N1 and P1 are $1 \mu m$ and $1.5 \mu m$. The output capacitance is $20 fF$.

For the nMOS we calculate $\beta$:
$$ C_{ox} = \frac{\varepsilon_{ox}}{t_{ox}} = \frac{3.9 * 8.85 * 10^{-14} F/cm}{10.5 * 10^{-8} cm} $$
$$ \beta = \mu_n C_{ox} \frac{W}{L} = 80 \frac{cm^2}{Vs} * C_{ox} * \frac{1 \mu m}{50nm} = 0.005294 \frac{A}{V^2} $$
We calculate $\frac{dV_B}{dt}$ in linear region
$$  \frac{dV_B}{dt} = - \frac{\beta}{C_B} \frac{(V_{DD} - V_t)^2}{2} = - \frac{0.005294 A/V^2}{20 fF} \frac{(1 - 0.3)^2}{2} $$
We calculate$\frac{dV_B}{dt}$ in saturation region
$$   \frac{dV_B}{dt} = - \frac{0.005294 A/V^2}{20 fF}  \left( 1 - 0.3 - \frac{0.6}{2} \right)0.6  $$
For $t_{pdf}$ we calculate the time that $V_B$ reaches to 0.5V. First from 1V to 0.7V
$$ \frac{0.7 - 1}{\Delta t_1} = - \frac{0.005294 A/V^2}{20 fF} \frac{(1 - 0.3)^2}{2}, \hspace{20pt} \Delta t_1 = 4.6 ps $$
Now from 0.7 to 0.5V
$$ \frac{0.5 - 0.7}{\Delta t_2} = - \frac{0.005294 A/V^2}{20fF} * (0.7 - \frac{0.6}{2})0.6 = 3.2 ps$$
So
$$ t_{pdf} = \Delta t_1 + \Delta t_2 = 7.8 ps $$


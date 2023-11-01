![[cs2.png|200]]
### Without Source Degeneration
---
Due to its transconductance, a MOSFET converts a gate voltage to a drain current. The drain current can then be converted to a output voltage with a resistor. 

When $V_{in}$ approaches $V_{th}$ the MOSFET turns on, drawing current from $R_d$ and lowering $V_{out}$. With no source resistor we have $V_{gs}  = V_{in}$. The transistor turns on in saturation since
$$ V_{in} > V_{th}, \hspace{20pt} V_{ds} > V_{in} - V_{th} $$
The drain current
$$ I_d = \frac{1}{2} \mu_n C_{ox} \frac{W}{L} (V_{in} - V_{th})^2 (1 + \lambda V_{ds}) $$
where $(1 + \lambda V_{ds})$ is channel length modulation. The output voltage is then
$$ V_{out} = V_{DD} - I_d R_d  $$
The transconductance in saturation
$$ g_m = \frac{2I_{ds}}{V_{in} - V_{th}} $$
The output expressed by $g_m$
$$ V_{out} = V_{dd} - g_m R_d $$
The input/output characteristics
$$ A_v = \frac{\partial V_{out}}{\partial V_{in}} = -g_m R_d $$
The small signal model for the saturation region
![[csmodel.png|500]]
As $V_{in}$ is increasing, $V_{out}$ drops more until $V_{in}$ exceeds $V_{out}$ by $V_{th}$ and the transistor operates in the linear/triode region
$$ V_{in} > V_{th}, \hspace{20pt} V_{ds} \leq V_{in} - V_{th} $$
in which case the drain current
$$ I_{d,linear} = \frac{1}{2} \mu_n C_{ox} \frac{W}{L} [2(V_{in} - V_{th})V_{ds} - V_{ds}^2](1 + \lambda V_{ds}) $$
and the output voltage
$$ V_{out} = R_d I_{d,linear} $$
in the linear/triode region the MOSFET ceases to act as an amplifier, and instead acts as a voltage controlled resistor.  When $V_{in} > V_{in1}$ the MOSFET is in linear region
![[triode.png|300]]
When the MOSFET is deep into the triode region $V_{out} \ll 2(V_{in} - V_{th})$ the resistance
$$ R_{on} = \frac{1}{\mu_n C_{ox} \frac{W}{L}(V_{in} - V_{th})} $$
So the output voltage
$$ V_{out,triode} = \frac{V_{dd}}{1 + \mu_n C_{ox} \frac{W}{L}R_d(V_{in} - V_{th})} $$
### Linearity
---
Since the transconductance varies with the input signal
$$ g_m = \mu_n C_{ox} (W/L)(V_{gs} - V_{th}) $$
the gain of the circuit changes with large variations in the input signal.

### Voltage Gain
---
The voltage gain
$$ A_v = -g_m R_d = - \sqrt{ 2_mu_n C_{ox} \frac{W}{L} } \frac{V_{R_d}}{\sqrt{I_d}} $$
where $V_{R_d}$ is the voltage drop across $R_d$. We see that the voltage gain can be increased by increasing $W/L$ or $V_{R_d}$ or decreasing $I_d$. 

- Increasing W/L leads to higher device capacitances.
- Increased $V_{R_d}$ reduces maximum voltage swing.
- Decreasing $I_d$ must lead to increase of $R_d$, leading to greater time constant at output.

### Channel Length Modulation
---
For large values of $R_d$, the effect of channel length modulation becomes significant. The voltage gain
$$ A_v = - g_m \frac{r_O R_d}{r_O + R_d} $$
where in saturation
$$ r_O = \frac{1}{\lambda I_d} $$
![[csmodu.png|500]]

### Current Source Load
---
The increase the voltage gain, the relationship
$$ A_v = -g_m R_d $$
suggests that we should increase $R_d$. This however reduces output voltage swing. To further increase gain we replace $R_d$ with a CCS that does not obey Ohm's law. The total impedance seen at the output node is equal to $r_{O1} || r_{O2}$, so
$$ A_v = -g_m (r_{O1}||r_{O2}) $$
![[csccs.png]]

### With Source Degeneration
---
The nonlinear dependence of the drain current upon the overdrive voltage $V_{ov} = V_{gs} - V_{th}$. To further linearize the device a source resistor can be used. 

As $V_{in}$ increased, so do $I_d$ and the voltage drop across $R_s$. A fraction of the change in $V_{in}$ appears across the resistor rather than as the gate-source overdrive, leading to a smoother variation of $I_d$. 

We intend to make the gain equation a weaker function of $g_m$. We define the equivalent transconductance of the circuit as
$$ G_m = \frac{g_m}{1 + g_m R_S} $$
the small-signal voltage gain is equal to
$$ A_v = -G_m R_d = - \frac{g_m R_D}{1 + g_m R_S} $$
At low current levels, $1/g_m \gg R_S$, so $G_m \approx g_m$. As the overdrive and therefore $g_m$ increase, the effect of degeneration $1 + r_m R_S$ becomes more significant. FOr large values of $V_{in}$, $I_D$ is approximately a linear function of $V_{IN}$ and $G_M$ approaches $1/R_S$. 
![[dege.png]]

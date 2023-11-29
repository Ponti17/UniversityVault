# Feedback Topologies
---
There are four "canonical" topologies described by Razavi. 

## Voltage-Voltage Feedback
---
![[Pasted image 20231127150536.png|300]]
This topology senses the output voltage and returns the feedback signal as a voltage. The feedback network is connected in parallel with the output and in series with the input. An ideal feedback network in this case exhibits
$$ R_{in} \to \infty, \hspace{20pt} R_{out} \to 0 $$
We can therefore write
$$ V_F = \beta V_{out},\hspace{10pt} V_e = V_{in} - V_F,\hspace{10pt} V_{out} = A_0(V_{in} - \beta V_{out}) $$
the transfer function
$$ \frac{V_{out}}{V_{in}} = \frac{A_0}{1 + \beta A_0} $$
We recognize $\beta A_0$ as the loop gain and that the overall gain has dropped by $1 + \beta A_0$.

**Output Impedance**
A negative-feedback system attempts to make the output an accurate (scaled) replica of the input. If we load an open-loop amplifier with a resistor $R_L$, the output would simply drop in proportion to $R_L/(R_L + R_{out})$. In the feedback system, $V_{out}$ remains as a reasonable replica of the input as long as the loop gain remains much greater than unity. 

It can be said that the feedback system "regulates" the output and stabilizes it despite load variations. For a voltage-voltage feedback system the output impedance is lowered by a factor $1 + \beta A_0$. 

## Current-Voltage Feedback
---

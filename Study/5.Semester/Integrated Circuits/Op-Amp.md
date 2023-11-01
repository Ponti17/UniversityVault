# Op-Amp Design
---

## Input Section
---
A typical MOSFET op-amp input section with CCS and current mirror load.
![[Pasted image 20231026084320.png|500]]

### Important Equations
---
The gain
$$ A_D = G_M R_{out}, \hspace{10pt} G_M = g_{m1,2}, \hspace{10pt} R_{out} = r_{o2} \parallel r_{o6} $$
We first must ensure all transistors are in saturation
$$ V_{GS} - V_{TH} < V_{DS} $$
When we have determined the overdrive voltage, we can determine the W/L
$$ I = \frac{1}{2} \mu_n C_{ox} \frac{W}{L} (V_{OD})^2 $$
### Example
---
Design for the following specifications
$$ SR = 10 \frac{V}{ms}, \hspace{10pt} GBW = 5 MHZ, \hspace{10pt} CMR = 0.5V, \hspace{10pt} V_{DD} = 1.8V, \hspace{10pt} C_L = 10pF$$
The slew-rate
$$ SR = \frac{I_{tail}}{C_L} $$
$$ P_1 = \frac{1}{R_{out} * C_L} $$
$$ GBW = \frac{g_{m1}}{C_L} $$
The current through M1 or M2 must be $I_{tail}/2$. The transconductance of $g_{m1,2}$
$$ g_{m1,2} = \sqrt{ 2 \mu C_{ox} (W/L) (I_{tail}/2) } $$
To satisfy the bandwidth
$$ 5 MHZ = \frac{g_m}{10 pF} \hspace{10pt} \Rightarrow \hspace{10pt} g_m = 50 \mu S $$
To satisfy the slew-rate
$$ SR = \frac{I_{tail}}{C_L} \hspace{10pt} \Rightarrow \hspace{10pt} I_{tail} = 100 \mu A  $$
The transconductance
$$ 50 \mu S = \sqrt{2 * 290 V^2/\mu A * (W/L) * I_{tail}/2 } \hspace{10pt} \Rightarrow \hspace{10pt} (W/L)_{1,2} = 0.086  $$
The common mode of the input should be half of VDD (0.9V). The Common-Mode-Range should be 0.5V. The maximum input
$$ 0.9 + 0.5/2 = 1.15V $$
The minimum input
$$ 0.9 - 0.5/2 = 0.65V $$
The maximum should be less than
$$ 1.15 < 1.8 - \sqrt{ \frac{I_{tail}}{\mu_p C_{ox} (W/L)_{5,6}} } $$
the minimum
$$ V_{in(min)} > \sqrt{ \frac{I_{tail}}{\mu_n C_{ox} (W/L)_{3,4}} } + \sqrt{ \frac{I_{tail}}{\mu_n C_{ox} (W/L)_{1,2}} } $$
$r_O$ of M2 and M6
$$ \frac{1}{0.15 V^{-1} * 50 \mu A} = 133 k\Omega, \hspace{20pt} \frac{1}{0.13 V^{-1} * 50 \mu A} = 154 k\Omega $$
The output impedance
$$ 133k \parallel 154k = 71.4k $$
The dominant pole
$$ P_1 = 1.4 MHz $$








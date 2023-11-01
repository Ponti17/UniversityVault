# Table of Contents
---


### Types
---
There are two types of amplifiers

**Small Signal Amplifiers**
- Very small input signals (typically nW)
- Important noise behaviour (low noise) and large gain
- Efficiency and power output not important
- Used in receivers
- Linear behaviour modeled by linear two-port parameters (s-param)
- Also called low-noise amplifier (LNA)

**Large Signal Amplifier
- Large output signals (typically mW to W)
- High output power, efficiency and large gain is important.
- Noise behaviour not important
- Used in transmitters
- Non-linear behaviour modeled by special non-linear models (e.g. Spice models)
- Also called power amplifier (PA)

### Parameters
---
Important parameters for microwave amplifiers include
- Gain $G$
- Noise Figure $F$
- 1dB Compression Point (Max Output Power)
- 3rd Order Intercept 
- Dynamic Range
- Input and Output match

### General Loaded Two-Port
---
![[twoportlna.png|600]]
Part of the incident wave going into the amplifier is reflected, and part of the amplified wave is reflected at the load. 

There are also reflections from waves propagating backwards into the source and backwards into the amplifier. We have 4 reflection coefficients.
$$ \Gamma_S, \hspace{20pt} \Gamma_{in}, \hspace{20pt} \Gamma_{out},\hspace{20pt} \Gamma_L $$
### Gain
---
![[gainlna.png]]
There are three gain definitions

**Power Gain**
Is the ratio of power dissipated in the load $Z_L$ to the power delivered to the input of the two-port network. The gain is independent of the source impedance $Z_s$. 
$$ G = \frac{P_L}{P_{in}} $$
**Available Gain**
Is the ratio of power available from the two-port network to the power available from the source. The gain depends on $Z_s$ but not $Z_L$.
$$ G_A = \frac{P_{av,s}}{P_{av,n}} $$
**Transducer Power Gain**
Is the ratio of power delivered to the load to the power available from the source. It depends on both $Z_L$ and $Z_s$.
$$ G_T = \frac{P_L}{P_{av,s}} $$
This parameter is usually most interesting, as we get to know how much power we end up with in the load with respect to the power delivered from the source.

### Gain Calculation
---
![[etmpar.png]]
The source impedance and load impedance are related to the reflection coefficients
$$ \Gamma_s = \frac{Z_s- Z_0}{Z_s + Z_0} $$
$$ \Gamma_L = \frac{Z_L- Z_0}{Z_L + Z_0} $$
The input reflection coefficient
$$ \Gamma_{in} = S_{11} + \frac{S_{12}S_{21}\Gamma_L}{1 - S_{22} \Gamma_L} $$
The output reflection coefficient
$$ \Gamma_{out} = S_{22} + \frac{S_{12}S_{21}\Gamma_s}{1 - S_{11}\Gamma_s} $$
The three gain equations

**Power Gain**
$$  G = \frac{P_L}{P_{in}} = \frac{|S_{21}|^2(1 - |\Gamma_L|^2)}{|1 - S_{22} \Gamma_L|^2 (1 - |\Gamma_{in}|^2)} $$
**Available Gain**
$$  G_A = \frac{P_{av,s}}{P_{av,n}} = \frac{|S_{21}|^2(1 - |\Gamma_s|^2)}{|1 - S_{11} \Gamma_s|^2 (1 - |\Gamma_{out}|^2)} $$
**Transducer Power Gain**
$$  G_T = \frac{P_L}{P_{av,s}} = \frac{|S_{21}|^2(1 - |\Gamma_s|^2)(1 - |\Gamma_L|^2)}{|1 - S_{22}\Gamma_L|^2 |1 - \Gamma_s \Gamma_{in}|^2} $$

### Matched Two Port
---
When the input and output networks are matched
$$ G_{T} = |S_{21}|^2 $$

### Unilateral Transistor
---
The forward gain is given by $S_{21}$. The backwards gain $S_{12}$.

Has no backward gain
$$ S_{12} = 0 $$
Now $\Gamma_{in} = S_{11}$ and $\Gamma_{out} = S_{22}$. The gain
$$ G_T = \frac{|S_{21}|^2 (1 - |\Gamma_s|^2) (1 - |\Gamma_L|^2)}{|1 - S_{11}\Gamma_s|^2 |1 - S_{22} \Gamma_L|^2} $$



# BFP420 Transistor Amp
---
A microwave amplifier using a single BFP420 must be designed. 

### Requirements
---
It must satisfy the following requirements:

**Transducer Power Gain**
$$ G_T = 15 dB \pm 0.25dB $$
in the frequency range $2.4GHz$ to $2.5Ghz$. 

**Reflection**
Input and output reflection
$$ |S_{11,amp}| \leq -10dB \hspace{20pt} |S_{22,amp} \leq -10dB $$
in the frequency range $2.4GHz$ to $2.5GHz$.

**Connections**
Input and output must use SMA connectors.

**Voltage**
External voltage of 3.0V. 

The amplifier must be built on a PCB of max size 5cm X 5cm. The material is FR4 with substrate height $0.51mm$. The parameters 
$$ \varepsilon_r = 4.5 \hspace{20pt} \tan \delta = 0.02 $$
### Components
---
The following components are available
Murata GRM15 kit B (0.5pF to 1uF C0G 0402)
Murata LQG15H (1.0nH to 120nH 0402)
Yageo SMD resistor ($0\Omega$ to $10M\Omega$ 0402)

VCE = 2V
kig indgang først

### Calc
---
![[twoportlna.png|600]]
The input and output reflection coeffecients
$$ \Gamma_{in} = S_{11} + \frac{S_{12}S_{21}\Gamma_L}{1 - S_{22} \Gamma_L} $$
$$ \Gamma_{out} = S_{22} + \frac{S_{12}S_{21}\Gamma_s}{1 - S_{11}\Gamma_s} $$
The conditions to obtain maximum transducer power gain
$$ \Gamma_S = \Gamma_{in}^* $$
$$ \Gamma_L = \Gamma_{out}^* $$
This is referred to as the simultaneous conjugate match conditions. We can wrtie
$$ \Gamma_S^* = S_{11} + \frac{S_{12}S{21}\Gamma_L}{1 - S_{22}\Gamma_L} $$
$$ \Gamma_L^* = S_{22} + \frac{S_{12}S_{21}\Gamma_S}{1 - S_{11} \Gamma_S} $$
Solving the above equations simultaneously gives the values $\Gamma_S$ and $\Gamma_L$ required for a simultaneous conjugate match. Calling these values $\Gamma_{MS}$ and $\Gamma_{ML}$ we get
$$ \Gamma_{MS} = \frac{B_1 \pm \sqrt{B_1^2 - 4|C_1|^2}}{2C_1} $$
$$\Gamma_{ML} = \frac{B_2 \pm \sqrt{B_2^2 - 4|C_2|^2}}{2C_2} $$
$$ B_1 = 1 + |S_{11}|^2 - |S_{22}|^2 - |\Delta|^2 $$
$$ B_2 = 1 + |S_{22}|^2 - |S_{11}|^2 - |\Delta|^2 $$
$$ C_1 = S_{11} - \Delta S_{22}^* $$
$$ C_2 = S_{22} - \Delta S_{11}^* $$
For an unconditionally stable two-port network, the solutions with a minus sign ($\Gamma_{MS}$ and $\Gamma_ML$) are the useful ones. 

The maximum transducer power gain under simultaneous conjugate match conditions is obtained with $\Gamma_S = \Gamma_{in}^* = \Gamma_{MS}$ and $\Gamma_L = \Gamma_{out}^* = \Gamma_{ML}$
$$ G_{T,max} = \frac{1}{1 - |\Gamma_{MS}|^2} |S_{21}|^2 \frac{1 - |\Gamma_{ML}|^2}{|1 - S_{22}\Gamma_{ML}|^2} $$
It can also be expressed as
$$ G_{T,max} = \frac{|S_{21}|}{|S_{12}|} (K - \sqrt{K^2 - 1}) $$
### Example
---
Design an amplifier to operate at 6GHz with maximum transducer power gain. The S parameters
![[Pasted image 20231026142530.png]]
First we determine K and $\Delta$
```
S11 = [0.641, -171.3]
S12 = [0.057, 16.3]
S21 = [2.058, 28.5]
S22 = [0.572, -95.7]
S = [S11, S12, S21, S22]
S_rect = np.zeros((2,2), dtype=complex)

for i in range(0, 4):
    if i < 2:
        S_rect[0][i] = np.round(cmath.rect(S[i][0], S[i][1] * np.pi/180),5)
    else:
        S_rect[1][i-2] = np.round(cmath.rect(S[i][0], S[i][1] * np.pi/180),5)

S = S_rect
S11, S12, S21, S22 = S[0][0], S[0][1], S[1][0], S[1][1]

delta = np.abs(S11*S22 - S12*S21)
num = 1 - np.abs(S11)**2 - np.abs(S22)**2 + delta**2
den = 2*np.abs(S12*S21)
K = num/den
print("Delta: " + str(delta))
print("K: " + str(K))
```
$$ \Delta = 0.3014 $$
$$ K = 1.504 $$
Since $K > 1$ and $|Delta| < 1$ the amp is unconditionally stable. The reflection coefficients for a simultaneous conjugate match are calculated

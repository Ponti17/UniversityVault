# Bias
---
We choose a simple passive bias network. The supply is 3V. We want to bias for $V_{CE} = 2V$, $I_C = 25 mA$ with the following network 
![[Pasted image 20231120122452.png]]
The DC current gain of BFP420
![[Pasted image 20231120115312.png]]
We set
$$ R_E = \frac{V_{CC} - V_{CE}}{I_C} = 40 \Omega $$
We set $V_{BB} = 1.5V$, and create a biasing network with $R_2 = 1k$ and $R_1 = 10k$ in parallel with a $1k$ pot. The emitter resistor
$$ R_E = \frac{V_{BB} - V_{BE}}{I_C} \approx 25 $$
The bypass cap we set to 1n. 
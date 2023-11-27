# Output CCS
---
CCS To keep transistors in best operating region,


The output CCS's replace R19/21 and R20/22. They consist of a depletion-mode MOSFET cascoded with a LM334 constant current source, as described by Walt Jung:

https://audioxpress.com/article/Sources-101-Audio-Current-Regulator-Tests-for-High-Performance-Full-Article

The circuit as describes by Walt Jung replacing LM317 with LM334. R_set should probably by 8.2R for about 9mA.

![[CCS_1.png]]

## LM334 Current
---
The total current is the sum of the current going through the SET resistor ($I_R$) and the LM334's bias current:

![[LM334.png]]

The ratio of $I_{set}$ to $I_{bias}$ is shown below

![[LM334_ratio.png]]

The current through $R_{set}$ is determined by $V_R$, which is approximately $214\mu V/K$ (64 mV @ 298K). 

![[LM334_VR.png]]

The current $I_{set}$ is then
$$ I_{set} = I_R + I_{bias} = \frac{V_R}{R_{set}} + I_{bias} = \left( \frac{V_R}{R_{set}} \right) \left( \frac{n}{n - 1} \right) $$
where $n$ is the ratio. Solving for $R_{set}$
$$ R_{set} = \frac{V_R \cdot n}{I_{set} (n - 1)} $$

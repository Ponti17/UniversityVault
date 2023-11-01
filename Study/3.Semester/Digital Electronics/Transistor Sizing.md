# Transistor Sizing
---
To archieve the best sizing for delay $t_{pdr} = t_{pdf}$ we first have to find:

- Worst case path while charging the output ($t_{pdr}$) i.e. the path with the maximum number of transistors between the output node and $V_{DD}$.

- Worst case path while discharging the output ($t_{pdf}$) i.e. the path with maximum number of transistors between the output node and GND.

We then have to find the ratio between the width of pMOS and nMOS transistors in worst case paths in a way that $t_{pdr} = t_{pdf}$. We consider that

- Two series transistors with similar size acts like a transistor with twice the length.

- Two transistors in parallel with similar size acts like a transistor with twice the width.

- The speed of pMOS is half the speed of nMOS with similar size ($\mu_n = 2 \mu_p$).

- Choose minimum length of technology as the length of all transistors.

We have the following formulas
$$ t_{pdr} = X \left( \frac{L}{W} \right)_p \left( \frac{1}{\mu_p}\right) $$
$$ t_{pdf} = X \left( \frac{L}{W} \right)_n \left( \frac{1}{2\mu_p}\right) $$
$$ L_n = L_p = L_{min} $$
$$ X = \frac{ C_{out} \frac{V_{DD}}{2}}{C_{ox} \frac{(V_{DD} - V_t)^2}{2} } $$
For the rest of the transistors (not in worst case path) we choose a width equal with the equavalent width of a branch which is in parallel. For example 
![[mos_ex.png]]
The left branch is the worst case. We know that two nMOS in series equal twice the length so
$$ \frac{3W}{2L} $$
So for the right transistor we choose $W = 3/2$.
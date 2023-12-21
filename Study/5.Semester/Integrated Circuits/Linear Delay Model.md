# Linear Delay Model
---
The normalized delay of a gate can be expressed in units of $\tau$ as
$$ d = f + p $$
$p$ is the parasitic delay inherent to the gate when no load is attached. $f$ is the effort delay or stage effort that depends on the complexity and fanout of the gate:
$$ f = gh $$
The complexity is represented by the logical effort $g$. An inverter is defined to have a logical effort of 1. 
$$ h = \frac{C_{out}}{C_{in}} $$
where $C_{out}$ is the capacitance of the external load being driven and $C_{in}$ is the input capacitance of the gate.
## Logical Effort
---
Logical effort of a gate is defined as the ratio of the input capacitance of the gate to the input capacitance of an inverter that can deliver the same output current.

### Example 1
For a three input NAND loaded with 5 NAND gates.
$$ g = \frac{5C}{3C} $$
$$ h = \frac{5hC}{5C} $$
$$ p = \frac{9C}{3C} = 3 $$
$$ d = gh + p = 5/3 h + 3 $$
$$ d_{abs} = 3RC(5/3h + 3) $$

### Example 2 
An inverter drives 4 three-input NAND gates with their inputs connected together.

**Inverter**
$$ g = 1 $$
$$ p = 1 $$
The three input NAND gate
![[Pasted image 20231204143602.png|400]]
Each NAND gate terminal has 5C, since the inputs are connected each gate contributes 15C. So
$$ h = \frac{4*3*5C}{3C} = \frac{60C}{3C} = 20 $$
So
$$ d = 1 *20 + 1 = 21 $$
$$ d_{abs} = 21 * 3RC = 63RC $$
## Multistage Logic Networks
---


### Example
![[Pasted image 20231204145221.png|400]]
$$ F = g_1 g_2 g_3 * b_1 b_2 * \frac{C_{out,path}}{C_{in,path}} $$
The logical effort
$$ g_1 = 4/3, g_2 = 5/3, g_3 = 5/3 $$
The branch
$$ b_1 = \frac{C_{on,path} + C_{off,path}}{C_{on,path}} = \frac{3 + (3 + 3)}{3} = 3  $$
$$ b_2 = \frac{2 + 2}{2} = 2 $$
So
$$ F = \frac{4}{3} \frac{5}{3} \frac{5}{3} (3)(2) \frac{45}{8} = 125 $$

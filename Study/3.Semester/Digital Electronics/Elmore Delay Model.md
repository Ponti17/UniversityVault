# Elmore Delay Model
---
For systems with a RC model of second or higher order we can use the Elmore delay model. We represent the circuit as an RC tree where

- Root: Voltage source
- Leaves: Capacitors
- Branches: Resistors

With the Elmore delay model the whole circuit will be considered as a first order RC circuit with the time constant
$$ \tau = \sum_i R_{is} C_i $$
Where $R_{is}$ is the effective resistance on the shared path from the source to $C_i$. For the example circuit
![[elmore1.png]]
we have
$$ \tau = \tau_1 + \tau_2 = R_1 C_1 + (R_1 + R_2) C_2 $$
When we know the time constant it is easy to calculate the propagation delay
$$ t_{pd} = \tau \ln(2) = 0.69 \tau $$

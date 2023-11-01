
# GRLV
---
![[GRLV_Schematic.png]]

## Specs
---
Max 1.5A continuous.

5v dropout voltage?

For 30V use 2 x 30VAC trafo.

## Output Voltage
---
Use 1/4W 0.1% 15ppm resistors for R7, R8, R9, R10.

Positive output voltage set by R7 and R8 multiplied by $10V$ reference voltage LT1021.
$$ V_o = \frac{R_8 + R_7}{R_7} * 10 $$
R7 Usually set to 1.5k so
$$ R_8 = \frac{V_o R_7}{10} - R_7 $$
Negative output voltage set by R9 and R10.
$$ V_o = \frac{R_9 + R_{10}}{R_{10}} * 10 $$
R10 is usually set to 1.5k so
$$ R_9 = \frac{V_o R_{10}}{10} - R_{10} $$
Output voltage can be trimmed using RV1 and RV2. 

### Common Resistor Values
---
| Voltage | R8 and R9 |
| ------- | --------- |
| 30V     | 3k        |
| 20V     | 1.5k      |
| 15V     | 750R      |
| 12V     | 300R          |

### Voltages below 12V
---
For voltage below 12V replace 1N4739A with 7V zener. Replace LT1021-10 with LT1021-7.
$$  V_{o,pos} = \frac{R_8 + R_7}{R_7} * 7 $$
$$  V_{o,neg} = \frac{R_9 + R_{10}}{R_{10}} * 10 $$
## Power LED
---
If power LED is not wanted omit the 2k resistors R13, R14 and the led D3.

## Transformer and Diode Bridge
---
For use with center tapped transformer only populate the middle diode bridge.

For transformer with two seperate output windings only populate two outer most diode bridges.

## Part Substitutes
---
OPA134 can be substituted by OPA445.

## Part Locations
---
![[GRLV_Bare.png]]

## Reference Picture
---
![[GRLV_Refernece_Pic.png]]
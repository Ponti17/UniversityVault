# RC Model for Delay Estimation
---
RC delay models approximate the IV and CV characteristics of transistor by replacing the transistor with resistor and capacitors.
![[RC_delay.png]]
The resistance of a transistor is proportional to $L$. We assume that gate and diffusion capacitances are equal $C_g = C_{dg} = C_{sb}$. A transistor of K times unit width has capacitance $KC$. In a 65nm process we roughly estimate C for a minimum length transistor to be $1 fF/\mu m$. 
![[rc_cap.png]]
For two inverters in series
![[inv_rc.png]]
we can finally reduce to
![[inv_rc_2.png]]

## Example
---
We want to convert the NAND gate to its RC model. We assume K = 3.
![[nand_cmos.png]]
For discharging all PMOS are open
![[rc_charge.png]]
We simplify
![[rc_char_sim.png]]
# CMOS
---
Logic circuits can be implemented using CMOS (Complementary MOS) which is a combination of PMOS and NMOS transistors. 

![PMOS_NMOS](pmos_nmos.png)

NMOS has a p-type substrate with regions of n-type. The majority carriers are electrons.
PMOS has a n-type substrate with regions of p-type. The majority carriers are holes.

![](nmos_pmos_sym.png "CMOS")
(a) = PMOS, (b) = NMOS

CMOS circuits consists of a pull-up network (PUN) that consists of PMOS transistors, and a pull-down network (PDN) that consists of NMOS transistors. PMOS Transistors conduct when the gate voltage is zero, and NMOS transistors conduct when the gate voltage is $V_{DD}$.

## Boolean Function Using CMOS
---
$\textrm{AND} \rightarrow \textrm{series connection}$
$\textrm{OR} \rightarrow \textrm{parallel connection}$

### Step by step implementation
1. Invert given function.
2. Construct PDN using NMOS.
3. Take the dual/complement of the inverted function i.e. $\textrm{AND} \rightarrow \textrm{OR}$ , $\textrm{OR} \rightarrow \textrm{AND}$.
4. Construct PUN using PMOS.
5. If all inputs end up inverted, non-inverted inputs can be used if CMOS output is inverted.
# Stability
---
## Oscillations
---
As a wave is reflected at the input at an amplifier it is reflected again at a source and so on. 
![[Pasted image 20231026113336.png|600]]
If $|\Gamma_S * \Gamma_{in}|> 1$, the series goes towards infinite, and oscillations will build up until it reaches saturation. 

Because $\Gamma_{in}$ and $\Gamma_{out}$ depends on the source and load matching, the stability of the amplifier depends on $\Gamma_S$ and $\Gamma_L$. There are two types of stability.

**Unconditional Stability**
If $|\Gamma_{in}| < 1$ and $|\Gamma_{out}| < 1$ for all passive source and load impedances (i.e. $|\Gamma_S| <1$ and $|\Gamma_L| < 1$).

**Conditional Stability**
If $|\Gamma_{in}| < 1$ and $|\Gamma_{out}| < 1$ for only a certain range of passive source and load impedances.

## Stability Conditions
---
We assume $\Gamma_S$ and $\Gamma_L$ can have any value, therefore $\Gamma_{in}$ must be less than one. 
$$ \Gamma_{in} = S_{11} + \frac{S_{12} S_{21} \Gamma_L}{1 - S_{22} \Gamma_L} < 1 $$
### Example
---
For a BFP420 the S-parameters
![[Pasted image 20231026114055.png]]
We change $Z_L$ such that the amplifier is stable. 

For the amplifier to be unconditionally stable the source and load reflection must satisfy
$$ |\Gamma_{in}| = \Biggl| S_{11} + \frac{S_{12} S_{21} \Gamma_L}{1 - S_{22} \Gamma_L} \Biggl| < 1 $$
$$ |\Gamma_{out}| = \Biggl| S_{22} + \frac{S_{12} S_{21} \Gamma_S}{1 - S_{11} \Gamma_S} \Biggl| < 1 $$
For a unilateral device this reduces to
$$ |S_{11}| < 1 $$
$$ |S_{22}| < 1 $$
### Bilateral Case
---
If $S_{12}$ is not zero, then we express the stability condition as
$$ \Biggl| S_{11} + \frac{S_{12} S_{21} \Gamma_L}{1 - S_{22}\Gamma_L} \Biggl| = 1 $$
Through lengthy calculations this reduces to
$$ \Biggl| \Gamma_L - \frac{(S_{22} - \Delta S_{11}^*)^*}{|S_{22}|^2 - |\Delta|^2} \Biggl| = \Biggl| \frac{S_{12} S_{21}}{|S_{22}^2 - |\Delta|^2} \Biggl|, \hspace{20pt} \Delta = S_{11}S_{22} - S_{12}S_{21}  $$
Essentially we have
$$ |\Gamma_L - C| = R $$
the load reflection minus some complex constant must equal a real constant. In the complex plane an equation of this form represents a circle where $C$ is the center and $R$ is the radius. The equations for the output stability circle with center $C_L$ and radius $R_L$
$$ C_L = \frac{(S_{22} - \Delta S_{11}^*)^*}{|S_{22}|^2 - |\Delta|^2}, \hspace{20pt} R_L = \Biggl| \frac{S_{12} S_{21}}{|S_{22}|^2 - |\Delta|^2} \Biggl| $$
The same applies for the input stability circle
$$ C_S = \frac{(S_{11} - \Delta S_{22}^*)^*}{|S_{11}|^2 - |\Delta|^2}, \hspace{20pt} R_S = \Biggl| \frac{S_{12} S_{21}}{|S_{11}|^2 - |\Delta|^2} \Biggl| $$
We can draw the circles on the Smith chart. When $S_{11}<1$ the point in the middle of the Smith chart represents stability so
![[Pasted image 20231029203328.png]]
When $S_{11}>1$ then
![[Pasted image 20231029203400.png]]

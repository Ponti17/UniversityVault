The boundary condition
$$ Z_L = \frac{V}{I} \Bigl|_{l = 0} = Z_0 \frac{V^+ + V^-}{V^+ - V^-} = Z_0 \left( \frac{1 + \Gamma(0)}{1 - \Gamma(0)}\right), \hspace{20pt} \Gamma(l) =\frac{V^- e^{-\gamma l}}{V^+ e^{\gamma l}}  $$
The reflection coefficient at the load end
$$ \Gamma_L = \Gamma(0) = \frac{Z_L - Z_0}{Z_L + Z_0} = \frac{V^-}{V^+} $$
depends upon the load impedance AND the characteristic impedance of the line. We see from the equation that if $Z_L = Z_0$ then $V^-/V^+=0$, and the reflection coefficient will be zero. 
$$ \Gamma_L = 0, \hspace{5pt} \textrm{when } Z_L = Z_0 $$
The characteristic impedance is therefore very important. The condition $Z_L = Z_0$ is called the matched load condition. The load impedance is matched to the transmission line characteristic impedance.  The power transfer is 100 percent.  The voltage and current expressed by the reflection coefficient
$$ V(l) = V^+ e^{\gamma l} (1 + \Gamma(l)) $$
$$ I(l) = \frac{V^+}{Z_0} e^{\gamma l} (1 - \Gamma(l)) $$
The impedance measured at a point of the line
$$ Z(l) = \frac{V(l)}{I(l)} = Z_0 \left( \frac{1 + \Gamma(l)}{1 - \Gamma(l)} \right) = Z_0 \left( \frac{Z_L \cosh(\gamma l) + Z_0 \sinh(\gamma l)}{Z_0 \cosh(\gamma l) + Z_L \sinh(\gamma l)} \right) $$
where
$$ \cosh \gamma l = \frac{e^{\gamma l} + e^{-\gamma l}}{2} $$
$$ \sinh \gamma l = \frac{e^{\gamma l} - e^{-\gamma l}}{2} $$
The normalized impedance
$$ \bar{Z}(l) = \frac{Z(l)}{Z_0} $$
The absolute impedances of a transmission line DONT mean anything. The first and most important thing is always the characteristic impedance. All impedances afterward are then normalized. The matched condition
$$ \textrm{If } \bar{Z}_L = 1 \hspace{10pt} \textrm{i.e.} \hspace{10pt} Z_L = Z_0, \hspace{20pt} \bar{Z}(l) = 1 \hspace{10pt} \Rightarrow \hspace{10pt} Z(l) = Z_0 $$
We see that the measured impedance will always be the characteristic impedance. The length of the line no longer matters when we have the matched condition. 

### Characteristic Impedance
---
The characteristic impedance is that impedance with which the is terminated, the impedance measured at any point on the line is equal to that terminating impedance. 




 
 
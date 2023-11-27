# Bilateral Specific Gain
---

### Unconditionally Stable Bilateral Case
---
We write $G_p$ (Power Gain) in the form
$$ G_p = |S_{21}|^2 g_p $$
where
$$ g_p = \frac{1 - |\Gamma_L|^2}{|1 - S_{22}\Gamma_L|^2 - |S_{11} - \Delta \Gamma_L|^2} = \frac{1 - |\Gamma_L|^2}{1 - |S_{11}|^2 + |\Gamma_L|^2 (|S_{22}|^2 - |\Delta|^2) - 2 Re(\Gamma_L C_2)} $$
and
$$ C_2 = S_{22} - \Delta S_{11}^* $$
Here $G_p$ and $g_p$ are functions of the device S parameters and $\Gamma_L$. The values of $\Gamma_L$ that produce a constant value of $g_p$ lie on a circle (operating power-gain circle). The equation for an operating power-gain circle in the $\Gamma_L$ plane is given by
$$ |\Gamma_L - C_p| = r_p $$
where the center of the circle
$$ C_p = \frac{g_p C_2^*}{1 + g_p(|S_{22}|^2 - |\Delta|^2)} $$
And the radius of the circle
$$ r_p = \frac{[1 - 2K|S_{12} S_{21}|g_p + |S_{12} S_{21}|^2g_p^2]^{1/2}}{|1 + g_p (|S_{22}|^2 - |\Delta|^2)} $$
The distance from the origin to the center of the circle is $|C_p|$ and the angle is $C_2^*$. The maximum operating power gain occurs at the value of $\Gamma_L$ when $r_p = 0$. 

For a given $G_p$, $\Gamma_L$ is selected from the constant operating power-gain circles. 

### Example
---
Design an amplifier to have an operating power gain of 9dB instead of $G_{T,max} = G_{p,max} = 11.38dB$. 
![[Pasted image 20231026142530.png]]
First we determine $g_p$. We design for $G_p = 9dB = 7.94$.
$$ g_p = \frac{G_p}{|S_{21}|^2} =\frac{7.94}{4.235} = 1.875 $$
We calculate Cp and rp and draw the circle on the smith chart. And choose a point on the edge of the circle.
![[Pasted image 20231102134832.png|500]]
We choose load reflection coefficient $\Gamma_L = 0.226 + 0.240j$. The required $\Gamma_s$ is then

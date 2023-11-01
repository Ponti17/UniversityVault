$$ V(x) = V^+ e^{-\gamma x} + V^- e^{+\gamma x}$$
$$  I(x) = I^+ e^{-\gamma x} + I^- e^{+\gamma x} $$
hvor den karakteristiske impedans
$$ Z_0 = \frac{V^+}{I^+} = - \frac{V^-}{I^-} $$
Ved $x = 0$
$$ V(0) = V^+ + V^- $$
$$ I(0) = I^+ + I^- $$
Et to-ports netværk kan beskrives med S-parametre.
![[twoport2.png]]
a og b er defineret som
$$ a_1 = \frac{V_1^+}{\sqrt{Z_0}}, \hspace{20pt} b_1 = \frac{V_1^-}{\sqrt{Z_0}} $$
$$ a_2 = \frac{V_2^+}{\sqrt{Z_0}}, \hspace{20pt} b_2 = \frac{V_2^-}{\sqrt{Z_0}} $$
Forhold givet ved S-parametre
![[spa.png]]
Udregning af S-parametre
$$ S_{11} = \frac{b_1}{a_1} \Bigg|_{a_2 = 0}, \hspace{20pt} S_{12} = \frac{b_1}{a_2} \Bigg|_{a_1 = 0} $$
$$ S_{21} = \frac{b_2}{a_1} \Bigg|_{a_2 = 0}, \hspace{20pt} S_{22} = \frac{b_2}{a_2} \Bigg|_{a_1=0} $$
Til beregning
$$ V_i = \sqrt{Z_0} a_i + \sqrt{Z_0} b_i $$
$$ I_i = \frac{V_i^+}{Z_0} - \frac{V_i^-}{Z_0} $$
$$ a_i = \frac{1}{2\sqrt{Z_0}} (V_i + Z_0 I_i) $$
$$ b_i = \frac{1}{2\sqrt{Z_0}}(V_i - Z_0 I_i) $$

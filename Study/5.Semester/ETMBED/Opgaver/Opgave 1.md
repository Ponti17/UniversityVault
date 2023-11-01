![[opg1.png]]
## Løsning
---
![[twoport2.png]]
$$ S_{21} = b_2/a_1 =\frac{V_2/V_1 - Z_0 I_2/V_1}{1 + Z_0 I_1/V_1} $$
Impedansens af kondensatoren
$$ Z_C = \frac{1}{j\omega C} $$
Kondensator parallel med $Z_0$. 
$$ Z_C || Z_0 = \frac{Z_0}{sCZ_0 + 1} $$
Udgangsspænding
$$ V_2 = V_1 \left( \frac{Z_0}{Z_0 + R + sCRZ_0} \right) $$
Størrelsen
$$ V_2/V_1 = \frac{Z_0}{Z_0 + R + sCRZ_0} $$
Strømmen
$$ I_1 = \frac{V_1}{Z_C || Z_0} $$
Forholdet
$$ I_1/V_1 = \frac{sZ_0C + 1}{Z_0} $$
Udgangsstrømmen
$$ I_2/V_1 = V_2/ Z_0 = -\frac{1}{sCRZ_0 + R + Z_0}$$
S-parametret
$$ S_{21} = \frac{2Z_0}{(sCZ_0 + 2)(CRZ_0 s + R + Z_0)} $$



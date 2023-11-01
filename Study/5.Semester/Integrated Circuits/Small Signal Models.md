### Basic Small Signal Model
---
![[smallsig.png|400]]

### Channel Length Modulation
---
![[smallsigmodu.png|400]]
Due to channel-length modulation, the drain current also varies with drain-source voltage. This effect can be represented by a resistor.
$$ r_O = \frac{1}{\frac{1}{2}\mu_n C_{ox} \frac{W}{L}(V_{GS} - V_{TH})^2 \lambda} \approx \frac{1}{\lambda I_D} $$
### Body Effect
---
![[smallsigbody.png|500]]
The bulk potential influences the threshold voltage and hence the gate-source overdrive. With all other terminals held at a a constant voltage, the drain current is a function of the bulk voltage. We can model this dependence by a current source with the value $g_{mb}V_{bs}$. In saturation
$$ g_{mb} = \mu_n C_{ox} \frac{W}{L} (V_{GS} - V_{TH}) \left( - \frac{\partial V_{TH}}{V_{BS}} \right) $$
Expressed by $\gamma, \Phi$
$$ g_{mb} = g_m \frac{\gamma}{2 \sqrt{2\Phi_F + V_{SB}}} = \eta g_m $$
where $\eta = g_{mb}/g_m$ and is typically around $0.25$. 
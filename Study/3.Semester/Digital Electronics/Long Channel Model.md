# Long Channel Model (Shockley)
---
A nMOS transistor has three regions of operation.

- Cutoff ($V_{gs} < V_t$), no path between drain and source.

- Linear ($V_{gs} > V_t, V_{gd} \geq V_t$), a channel is created beneath the gate. $I_{ds}$ increased with both drain and gate voltages.

- Saturation ($V_{gs} > V_t, V_{gd} < V_t$), The channel becomes pinched off. $I_{ds}$ is controlled only by gate voltage.

According to the long channel model the drain-source current at the different operation regions are
![[long_channel_nmos.png]]
![[long_channel_pmos.png]]

## Drain-Source Current in Linear Region
---
To calculate $I_{ds}$ of nMOS in linear region we first need to calculate

1. The amount of charge in the channel ($Q_{channel}$)
2. The rate at which it moves.

The gate-channel acts like a capacitor. The charge on each plate of a capacitor is $Q=CV$. So the charge in the channel $Q_{channel}$ is
$$ Q_{channel} = C_g (V_{gc} - V_t) $$
Where $C_g$ is the capacitance of the gate to channel. $V_{gc}$ is the voltage difference between gate and channel. We can calculate $V_{gc}$ as
$$ V_{gc} = V_{gs} - \frac{V_{ds}}{2} $$
The capacitance of a capacitor
$$ C_g = \varepsilon \frac{A}{t} $$
![[cap_fig.png]]

If the gate has length $L$ and width $W$ and the oxide thickness is $t_{ox}$, the capacitance is
$$ C_g = k_{ox} \varepsilon_0 \frac{WL}{t_{ox}} = \varepsilon_{ox} \frac{WL}{t_{ox}} = C_{ox} WL $$
$\varepsilon_0 = 8.85*10^{-14} F/cm$ is the permittivity of free space. $k_{ox}$ is 3.9 for $SiO_2$, so the permittivity of $SiO_2$ is $\varepsilon_{ox} = 3.9 \varepsilon_0$. Often the term $\varepsilon_{ox}/t_{ox}$ is called $C_{ox}$, the capacitance per unit area of gate oxide. Using the equations
$$  Q_{channel} = C_g (V_{gc} - V_t)  $$
$$  V_{gc} = V_{gs} - \frac{V_{ds}}{2}  $$
$$  C_g = C_{ox} WL $$
The charge in the channel in the linear region
$$ Q_{channel} = C_{ox} WL \left( V_{gs} - \frac{V_{ds}}{2} - V_t \right)  $$
The drain-source curent $I_{ds}$ is the total amount of electron charge in the channel divided by the time required to cross
$$ I_{ds} = \frac{Q_{channel}}{L/v} $$
$v$ is the average velocity of electron carriers in the channel. $v$ is proportional to the lateral electric field
$$ v = \mu E $$
where $\mu$ is the mobility of electrons (typically 500-700 $cm^2/Vs$). The electric field $E$ is the voltage difference between drain and source $V_{ds}$ divided by channel length
$$ E = \frac{V_{ds}}{L} $$
So the average velocity of electron carriers in the channel
$$ v = \mu \frac{V_{ds}}{L} $$
So the drain-source current in the linear region is
$$  I_{ds} = \frac{Q_{channel}}{L/v} = \mu C_{ox} \frac{W}{L} \left( V_{gs} - V_t - \frac{V_{ds}}{2} \right) V_{ds} = \beta \left( V_{gs} - V_t - \frac{V_{ds}}{2} \right) V_{ds} $$
where
$$ \beta = \mu C_{ox} \frac{W}{L} $$

## Drain-Source Current in Saturation Region
---
By increasing $V_{ds}$, $I_{ds}$ will increase in linear region until pinch off at the drain side. At this point $I_{ds}$ will be independent of $V_{ds}$. At pinch off
$$ V_{ds} = V_{gs} - V_t $$
Using the equation
$$   I_{ds} = \beta \left( V_{gs} - V_t - \frac{V_{ds}}{2} \right) V_{ds} $$
We get
$$    I_{ds} = \beta \left( V_{gs} - V_t - \frac{V_{gs} - V_t}{2} \right) (V_{gs} - V_t) = \frac{\beta}{2} (V_{gs} - V_t)^2 $$


# Electrostatics

Electrostatics is the branch of electromagnetics that deals with phenomena associated with static electricity. Electrostatics stem from the simple fact that charges exert forces on one another. 

## Coulomb's Law

The electric force $F_{e12}$ on a point charge $Q_2$ from a point charge $Q_1$ in vacuum or air is given by
$$ F_{e12} = \frac{1}{4 \pi \epsilon_0} \frac{Q_1 Q_2}{R^2} \hat{R}_{12} $$
where $R$ is the distance between the charges, $\hat{R}_{12}$ is the unit vector pointing from $Q_1$ to $Q_2$ and $\epsilon_0 = 8.8542 \textrm{ pF/m}$.

If we have more than two point charges we can use the principle of superposition i.e. the combined force exerted on a charge is a sum of the individual forces. 

## Electric Field Intensity Vector

To describe the electric field we introduce the electric field intensity vector. It is equal to the electric force $F_e$ on a point charge $Q_p$ placed in the electric field, divided by $Q_p$
$$ E = \frac{F_e}{Q_p}, \hspace{10pt} Q_p \rightarrow 0 $$
The unit for the electric field intensity vector is V/m. From Coulomb's law we obtain the following expression for the electric field intensity vector of a point charge $Q$ at a distance $R$ from the charge
$$ E = \frac{1}{4 \pi \epsilon_0} \frac{Q}{R^2} \hat{R} $$
![[electric_field_intensity_vector.png]]
By superposition the electric field intensity vector from several charges is
$$ E = E_1 + E_2 + \ldots + E_N = \frac{1}{4 \pi \epsilon_0} \sum_{i=1}^N \frac{Q_i}{R_i^2} \hat{R}_i $$
where $\hat{R}_i$ are the corresponding unit vectors.

## Continous Charge Distributions


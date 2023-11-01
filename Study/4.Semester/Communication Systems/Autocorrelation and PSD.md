Autocorrelation is the average of the multiplication of two values of a random variable.
$$ R_x(t_1, t_2) = E[X(t_1), X^*(t_2)] $$
If its a Wide Sense Stationary signal (constant mean and variance) only the difference between $t_1$ and $t_2$ matters
$$ R_x(\tau) = E[X(t), X^*(t+\tau)] $$
The PSD
$$ S_X(f) = \mathcal{F} \{ R_x(\tau) \} $$
For a digital transmission with random values $+A$ and $-A$, and random offset $t_0$
![[dig1.png]]
Since we are dealing with a WSS function we pick any time $t$. At $\tau = 0$ the autocorrelation function is either $A*A=A^2$ or $(-A)*(-A)=A^2$. At $\tau = T$ we are certain that a we are looking at a different random bit. So
![[auto1.png]]
The PSD is simply the FT. A triangle consists of the convolution of two squares. So the FT is a squared sinc function.
![[sinc2.png]]
The PSD shows the average power used as a function of frequency. What we see is that if $T$ is small i.e. fast transmission, the bandwidth used is wide.
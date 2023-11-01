We consider a random signal $X$. We're looking a the signal at two different times $t_1$ and $t_2$. 
$$ R_x(t_1, t_2) = E[X_{t_1}, X^*_{t_2}] $$
![[ranwave.png]]
We consider some arbitrary random waveforms. At time $t_1 = t_2 = 0$, we get
$$1 * 1 = 1, \hspace{20pt}-1 * (-1) = 1, \hspace{20pt}-1 * (-1) = 1, \hspace{20pt} $$
At $\tau = t_2 - t_1$ we get 1.
![[autoco.png]]
For a random waveform from 1v to 3v
![[auto2.png]]
At $t_1 = t_2$ we either get $1*1=1$ or $3*3 = 9$, so the autocorrelation function is $(1+9)/2 = 5$. As time goes on we either get $3*3=9$, $1*1=1$, $1*3=3$,$3*1=3$. So the autocorrelation function $(9+1+3+3)/4=4$.
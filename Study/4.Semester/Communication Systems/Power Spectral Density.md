The power spectral density (PSD) is defined as
$$ S_x(f) = \lim_{T \to \infty} \frac{E[\,|F_{X_T}(f)|^2]}{2T} $$
The expected value function (E) is like taking an average. If we take the integral over all the frequencies
$$ \bar{X^2} = \int_{-\infty}^\infty S_x(f) df $$
then we get the mean squared value i.e. the average power. If we truncate an infinite signal
$$ X_t = \begin{cases} 
X(t), \hspace{20pt} |t| \leq T \leq \infty, \\
0, \hspace{35pt} |t| > T
\end{cases} $$
we call the Fourier transform
$$ F_{X_t}(f) = \int_{-\infty}^\infty X_t(t) e^{-j 2 \pi f t} dt, \hspace{20pt} T < \infty$$
The PSD is the Fourier transform of the autocorrelation function
$$ S_x(f) = \mathcal{F} \{ R_x(\tau) \} $$
The autocorrelation function of white noise is a delta-function at $\tau = 0$, since there is NO correlation between values. The Fourier transform of a delta function is constant. White noise contains all frequencies.
![[autopsd.png]]

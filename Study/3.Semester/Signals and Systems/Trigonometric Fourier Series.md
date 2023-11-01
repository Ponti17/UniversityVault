# Trigonometric Fourier Series
---
The trigonometric fourier series is only for periodic signals. Consider a periodic signal as a sum of average value (DC), cosine terms and sine terms.
$$ x(t) = dc + \cos + \sin$$
$\Updownarrow$
$$ x(t) = a_0 + \sum\limits_{n=1}^{\infty} a_n \cos(n\omega_0 t) + \sum\limits_{n=1}^{\infty} b_n \sin(n \omega_0 t) $$
The term $a_0$ is the DC value of the signal obtained from dividing the total area of one time period with the time period.
$$ a_0 = \frac{1}{T_0}\int_{T_0} x(t) dt $$
The cos/sin Fourier coefficients
$$ a_n = \frac{2}{T_0}\int_{T_0} x(t) \cos(n\omega_0 t) dt $$
$$ b_n = \frac{2}{T_0} \int_{T_0} x(t) \sin(n \omega_0 t) dt $$
If we consider the expansion
$$ x(t) = 4 + 3\cos(2 \omega_0 t) + 5\sin(2\omega_0 t) + 4 \cos(3 \omega_0 t) + 2 \sin(3 \omega_0 t) + ... $$
We see the term $a_0 = 4$. The terms $3\cos(2\omega_0 t)$, $5 \sin(2 \omega_0 t)$ are the second harmonics. The terms $4\cos(3 \omega_0 t)$, $2\sin(3\omega_0 t)$ are the third harmonics. We see that amplitude of the second harmonic cosine term is
$$ a_2 = 3 $$
and the amplitude of the second harmonic sine term is
$$ b_2 = 5 $$
## Fourier Coefficients Examples
---
If the signal $x(t)$ is symmetrical about $t$-axis then $a_0 = 0$.

If $x(t)$ is a purely even, $x(-t) = x(t)$, then $b_n = 0$.

If $x(t)$ is a purely odd, $x(-t) = -x(t)$, then $a_n = 0$.

**Example 1, Square Wave**
![[fourier_ex1.png]]
We see the signal is symmetrical about the $t$-axis and $y$-axis i.e. the signal is even and has no DC component
$$ a_0 = 0, \hspace{20pt} b_n = 0$$
So
$$ x(t) = \sum\limits_{n=1}^{\infty} a_n \cos(n \omega_0 t)$$
The fourier coefficient
$$ a_n = \frac{2}{T_0} \int_{T_0} x(t) \cos(n \omega_0 t) dt$$
We see the fundamental time period is $T_0 = 4$. First we calculate the angular frequency
$$ \omega_0 = \frac{2\pi}{T_0} = \frac{2\pi}{4}= \frac{\pi}{2} $$
The integral
$$ a_n = \frac{1}{2} \int_{-1}^{3}x(t) \cos\left(n \frac{\pi}{2}t\right)dt $$
We split the integral as we can't integrate over discontinuities.
$$ a_n = \frac{1}{2} \left[ \int_{-1}^{1} 1 \cos\left(n \frac{\pi}{2} t\right) dt + \int_{1}^{3} -1 \cos\left(n \frac{\pi}{2} t\right) dt \right] $$
$$ a_n = \frac{1}{2} \left[ \int_{-1}^{1}\cos\left(n \frac{\pi}{2} t\right) dt - \int_{1}^{3} \cos\left(n \frac{\pi}{2} t\right) dt \right] $$
We now define a new variable
$$ \theta = \frac{n\pi}{2} t $$
Since $\frac{n\pi}{2}$ is constant, when $t$ gets infinitely small $t \rightarrow dt$
$$ \frac{n\pi}{2}dt = d\theta, \rightarrow dt = \frac{2}{n\pi} d\theta $$
We now substitute
$$ a_n = \frac{1}{2} \left[ \int_{\frac{-n\pi}{2}}^{\frac{n\pi}{2}} \cos(\theta) \frac{2}{n\pi} d\theta - \int_{\frac{n\pi}{2}}^{\frac{3n\pi}{2}} \cos(\theta) \frac{2}{n\pi} d\theta \right] $$
We move constants out of the integrals
$$ a_n = \frac{1}{2} \frac{2}{n\pi} \left[ \int_{\frac{-n\pi}{2}}^{\frac{n\pi}{2}} \cos \theta d\theta - \int_{\frac{n\pi}{2}}^{\frac{3n\pi}{2}}\cos \theta d\theta \right] $$
We integrate
$$ a_n = \frac{1}{n\pi} \left[ (\sin \theta)_{\frac{-n\pi}{2}}^{\frac{n\pi}{2}} - (\sin \theta)_{\frac{n\pi}{2}}^{\frac{n\pi}{2}} \right] $$
We put in the limits
$$ a_n = \frac{1}{n\pi} \left[ \sin\left(\frac{n\pi}{2}\right) - \sin\left(\frac{-n\pi}{2}\right) - \sin\left(\frac{3n\pi}{2}\right) + \sin\left( \frac{n\pi}{2} \right) \right] $$
**Example 2, Sawtooth**
![[fourier_ex2.png]]
We see this signal is not symmetrical about $t$-axis. If the signal is flipped about the $y$-axis it is not identical so it is not pyrelu even. It is also not purely odd. So we assume
$$ a_0 \neq 0, \hspace{20pt} a_n \neq 0, \hspace{20pt} b_n \neq 0 $$
We see the fundamental time period
$$ T_0 = 2\pi $$
We calculate the signal average
$$ a_0 = \frac{1}{T_0} \int_{T_0} x(t) dt = \frac{1}{2\pi}\int_0^{2\pi} \frac{t}{2\pi} dt = \frac{1}{4\pi^{2}} \left[ \frac{t^{2}}{2}\right]_0^{2\pi} = \frac{1}{2} $$
The angular frequency
$$ \omega_0 = \frac{2\pi}{T_0} = \frac{2\pi}{2\pi} = 1 $$
the second fourier coefficients
$$ a_n = \frac{2}{2\pi} \int_0^{2\pi} \frac{t}{2\pi} \cos(nt) dt = \frac{1}{2\pi^{2}} \int_0^{2\pi} t \cos(nt) dt = 0$$



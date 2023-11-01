# Complex Exponential Fourier Series
---
A signal can be represented as a sum of complex exponentials
$$ x(t) = \sum\limits_{n=-\infty}^{\infty} c_n e^{jn\omega_0 t} $$
where $c_n$ is the complex exponential Fourier coefficient.
$$ c_n = \frac{1}{T_0} \int_{T_0} x(t) e^{-jn\omega_0 t} dt $$
If we reverse $c_n$ ($n = -n$)
$$ c_{-n} = \frac{1}{T_0} \int_{T_0} x(t) e^{jn\omega_0 t} dt$$
We then perform the conjugate operation
$$ c_{-n}^{\ast} = \frac{1}{T_0} \int_{T_0} x^{\ast}(t) e^{-jn\omega_0 t} dt $$
if $c_n$ is conjugate symmetric
$$ c_n = c_{-n}^\ast $$
then
$$ x(t) = x^{\ast}(t)$$
and is real. (no imaginary part). If the magnitude
$$ |c_n| = |c_{-n}| $$
then $c_n$ is even. If the angle
$$ -\angle c_n = \angle c_{-n} $$
then $c_n$ is odd. Consider the signal

$$ x(t) \rightarrow c_n = n^{2}e^{jn^3} $$
Since $n^2$ is even and $n^3$ is squared it implies that $c_n$ is conjugate symmetric i.e. $x(t)$ is real.
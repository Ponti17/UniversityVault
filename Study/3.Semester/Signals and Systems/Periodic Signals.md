# Periodic Signals
---
A signal is said to be periodic if it repeats itself after a regular interval of time e.g.
$$ \Delta t = 5, \hspace{20pt} x(t) = x(t + 5) $$
## Condition of Periodicity of Continous Time Signals
---
For a continous time signal to be discreet the following has to be true.
$$ x(t) = x(t \pm nT_0) $$
where $n$ is an integer and $T_0$ is the fundemental period, the smallest positive value of time for which a the signal is periodic. 

The fundamental frequency
$$ f_0 = \frac{1}{T_0} $$
The fundamental angular frequency
$$ \omega_0 = 2\pi f_0 $$
or
$$ \omega_0 = \frac{2\pi}{T_0} $$
## Condition of Periodicity of Discreet Time Signals
---
For a discreet time signal to be periodic the following has to be true
$$ x[n] = x[n \pm mN] $$
where $m$ is an integer and $N$ is the fundamental period of the signal. For discreet signals $N$ **must** be an integer.

The fundamental frequency
$$ F = \frac{1}{N} $$

## Calculation of Fundamental Period
---
We have the condition
$$ x(t) = x(t + T_0) $$
We consider the signal
$$ x(t) = A_0 e^{j \omega_0 t} $$
The signal is periodic so
$$ x(t) = A_0 e^{j \omega_0 (t + T_0)} $$
We now have the expression 
$$ A_0 e^{j \omega_0 t} = A_0 e^{j \omega_0 (t + T_0)} $$
$\Updownarrow$
$$ e^{j \omega_0 t} = e^{j \omega_0 (t + T_0)} $$
$\Updownarrow$
$$ e^{j \omega_0 t} = e^{j \omega_0 t} e^{j \omega_0 T_0} $$
$\Updownarrow$
$$ e^{j \omega_0 T_0} = 1 $$
From Eulers equation we know that
$$ e^{jx} = \cos(x) + j \sin(x) $$
If we set $x = 2\pi k$
$$ e^{j2 \pi k} = \cos(2 \pi k) + j \sin(2 \pi k) $$
$\Updownarrow$
$$ e^{j2 \pi k} = 1 $$
So we have
$$  e^{j \omega_0 T_0} = e^{j 2 \pi k} $$
We see now that
$$ \omega_0 T_0 = 2 \pi k $$
or
$$ T_0 = \frac{2 \pi k}{\omega_0} $$
If $k = 1$ then
$$ T_0 = \frac{2\pi}{\omega_0} $$
## Examples
---
Consider the signal
$$ x(t) = \sin^2(4\pi t) $$
We know that
$$ \cos(2 \theta) = 1 - 2 \sin^2 \theta $$
So
$$ \sin^2 \theta = \frac{1}{2} [ 1 - \cos 2 \theta] $$
Where $\theta = 4\pi t$.
$$ x(t) = \sin^2(4 \pi t) = \frac{1}{2} [ 1 - \cos(8 \pi t)] $$
$$ x(t) = \frac{1}{2} - \frac{\cos 8 \pi t}{2} $$
We see that the signal has two even compoentns. The fundamental frequency for cosine
$$ T_0 = \frac{2\pi}{8 \pi} = 0.25 $$

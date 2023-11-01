# Transfer Function
---
The transfer function is defined as the ratio of Laplace transform of output to the Laplace transform of input, when all initial conditions are assumed to be zero.

The transfer function $H(s)$ is closely related to the impulse response $h(t)$.
$$ \mathcal{L}\{h(t)\} = H(s), \hspace{20pt} \mathcal{L}^{-1}\{H(s)\} = h(t)$$
## Calculation
**Example 1, Non-linear:**
We consider the output
$$ y(t) = x(t-1) + 5u(t)$$
The Laplace transform
$$ \mathcal{y(t)} = Y(s) = X(s) e^{-s} + \frac{5}{s}$$
We see now that the transfer function is not calculable
$$ H(s) = \frac{Y(s)}{X(s)}$$
since $X(s)$ would not dissappear after divison. This is because the system is non-linear. 

**Example 3:**
We consider the output
$$ y(t) = x(t-1) + x(t+2)$$
The Laplace transform
$$ \mathcal{L} \{ y(t) \} = Y(s) = X(s)e^{-2s} + X(s) e^{2s} = X(s) (e^{-2s} + e^{2s})$$
The transfer function
$$ H(s) = \frac{Y(s)}{X(s)} = e^{-2s}+ e^{2s}$$
We now take the inverse Laplace transform to get the impulse response
$$ h(t) = \delta(t - 2) + \delta(t + 2)$$

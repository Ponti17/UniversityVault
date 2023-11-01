# Impulse Response
---
The impulse response is only valid for LTI systems. It is the output of the system when the input is the unit impulse $\delta(t)$.
$$ \delta(t) \rightarrow SYS \rightarrow h(t) $$
The impulse response is fixed for a LTI system. If the input/output relationship of a system is known it is easy to calculate the impulse response.
## Impulse Response Calculation
---
$$ y(t) = \int_{\infty}^{t} x(\tau) d\tau$$
We perform Laplace
$$ Y(s) = \frac{X(s)}{s}$$
The transfer function
$$ H(s) = \frac{1}{s}$$
We perform inverse Laplace
$$ h(t) = \mathcal{L}^{-1}\{H(s)\} = u(t)$$
## Convolution
---
If system relationship is unknown
$$ y(t) = \hspace{3pt}?$$
But the impulse response is known the output can be calculated as the convolution sum
$$ y(t) = h(t) * x(t)$$
where $\ast$ is the convolution operator. This is because the tranfer function
$$ H(s) = \frac{Y(s)}{X(s)} \rightarrow Y(s) = H(s) X(s)$$
Taking the inverse laplace
$$ \mathcal{L}^{-1}\{ H(s) X(s) \} = h(t) * x(t)$$

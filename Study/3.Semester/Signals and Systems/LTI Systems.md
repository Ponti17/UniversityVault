## Linear Time-Invariant System Prerequisites
---
- System linearity is independent of time scaling.
- System linearity is independent of coefficient used in system relationship.
- If an added/subtracted term other than input and output is available in the system relationship then the system will be nonlinear.
- If output is summation of time shifted terms of input, then the system will be linear.
- Integral and differential operators are linear operators.
- Even and odd operators are linear operators.
- Real, Imaginary and Conjugate operators are nonlinear operators.
- No time scaling
- Coefficient in system relationship should be constant.
- Any added/subtracted term in the system relationship must be constant or zero.

## Transfer Function and Impulse Resposne
---
Transfer functions and impulse response are ONLY for LTI systems. They are used to characterize the system. 

Consider the output of a system
$$ y(t) = x(t-1) + x(t + 1)$$
We convert to frequency domain with Laplace transform
$$ Y(s) = X(s) e^{-s} + X(s) e^{s}$$
The transfer function is defined as (when all initial conditions are 0)
$$ H(S) = \frac{Y(s)}{X(s)} = e^{-s}+ e^{s}$$
With the inverse Laplace transform we convert back and get the impulse response
$$ h(t) = \delta(t-1) + \delta(t + 1)$$
The impulse response is
$$ \delta(t) \rightarrow h(t) $$
The transfer function can be determined using either Fourier or Laplace transform. If using Fourier the transfer function is denoted $H(_\omega)$. 

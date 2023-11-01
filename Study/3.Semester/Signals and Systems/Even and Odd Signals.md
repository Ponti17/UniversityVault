## Even Signals
---
Even signals remain identical under time reversal. (reflecting over y-axis)
$$ x(t) \rightarrow x(-t) = x(t) $$
this must be true for all values of $t$. The signal $\cos(\omega t)$ is even.
![[cos_even.png]]

## Odd Signals
---
Odd signals does not remain identical under time reversal. i.e. they are asymmetrical over the y-axis.
$$ x(t) \neq x(-t) $$
For odd signals the time reversal
$$ x(-t) = -x(t) $$
or
$$ x(t) = -x(-t) $$
All odd signals pass through the origin
$$ x(t) = 0, \hspace{20pt} t = 0 $$
The DC value (average) of any odd signal is 0. The signal $\sin(\omega t)$ is odd
![[sin_odd.png]]

## Sum of Odd and Even Signals
---
Often signals are neither even nor odd, but have both even and odd components.

Any signal can be represented as a sum of odd and even signals.  If a signal $x(t)$ has the even component $x_e(t)$ and odd component $x_o(t)$ then
$$ x(t) = x_e(t) + x_o(t) $$
If we set $t = -t$ we have
$$ x(-t) = x_e(-t) + x_o(-t) $$
$\Updownarrow$
$$ x(-t) = x_e(t) - x_o(t) $$
To find the even component
$$ x(t) + x(-t) = 2x_e(t) $$
$\Updownarrow$
$$ x_e(t) = \frac{1}{2} \left[ x(t) + x(-t) \right] $$
To find the odd component
$$ x(t) - x(-t) = 2x_o(t) $$
$\Updownarrow$
$$ x_o(t) = \frac{1}{2} \left[ x(t) - x(-t) \right] $$

## Properties of Even and Odd Signals
---
If a signal has an odd power it is odd, if it has an even power it is even.

### Even/Odd Components of DC Value
For the function $x(t) = 10$, we know that
$$ x(t) = x(-t) $$
Which is a property of even signals. So DC signals are even with the components
$$ x_e(t) = \frac{1}{2} [x(t) + x(-t)] = \frac{1}{2} 20 = 10 $$
$$ x_o(t) = \frac{1}{2}[x(t) - x(-t)] = 0 $$
### Addition of Even Signals
Consider the example
$$ x(t) = 10 + t^2 $$
We perform time reversal
$$ x(-t) = 10 + (-t)^2 $$
So
$$ x(t) = x(-t) $$
The sum of two even signals result in an even signal.

### Addition of Even and Odd Signals
Consider the example
$$ x(t) = 10 + t^3 $$
We perform time reversal
$$ x(-t) = 10 - t^3 $$
We see that
$$ x(t) \neq x(-t), \hspace{20pt} x(t) \neq -x(-t) $$
The sum of an even and odd signal we get something that is neither even nor odd.

### Multiplication of Even Signals
Consider the example
$$ x(t) = t^2 t^4 = t^6 $$
We perform time reversal
$$ x(-t) = (-t)^6 = t^6 = x(t) $$
So the product of two even signals is an even signal.

### Multiplication of Odd Signals
Consider the example
$$ x(t) = t^3 t^5 = t^8 $$
We perform time reversal
$$ x(-t) = (-t)^8 = t^8 = x(t) $$
So the product of two odd signals is an even signal.

### Multiplication of Odd and Even Signal
Consider the result
$$ x(t) = t^3 t^6 = t^9 $$
We see that the result has an odd power. So the product of an odd and even signal is an odd signal.

### Differentiation of Even Signals (Not valid for DC)
Differentiation of an even signal gives an odd signal.
$$ (t^4)' = 4t^3 $$

### Differentiation of Odd Signals (Not valid for DC)
Differentiation of an odd signal gives an even signal
$$ (t^3)' = 3t^2 $$

### Integration of Even Signal
Integration of an even signal gives an odd signal
$$ \int t^4 dt = \frac{t^5}{5} + C $$

### Integration of Odd Signal
Integration of an odd signal gives an even signal
$$ \int t^3 dt = \frac{t^4}{4} + C $$

### Fraction of Odd Signal
The fraction of an odd signal is an odd signal. If we let O be an odd signal
$$ \frac{1}{O} = O $$

### Fraction of Even Signal
The fraction of an even signal is an even signal. If we let E be an even signal
$$ \frac{1}{E} = E $$ 

# Convolution
---
A convolution is an integral that expresses the amount of overlap of one function when it is shifted over another function.
$$ y(t) = h(t) * x(t) = \int_{-\infty}^{\infty} x(\tau) h(t-\tau) d\tau $$
To perform convolution we first replace $t$ with a dummy variable $\tau$.
$$ x(t) \rightarrow x(\tau), \hspace{20pt} h(t) \rightarrow h(\tau)$$
For the impulse response we perform Time Reversal
$$ h(\tau) \rightarrow h(-\tau)$$
We then perform time shifting on the impulse response (We know that we can only perform signal operations on the original variable)
$$ h(-\tau) \rightarrow h(-(\tau - t)) =h(t - \tau)$$
Consider the input $x(t)$ and the impulse response $h(t)$. 

## Example, Shortcut
---
We know the following

- Convolution of two rectangular pules of unequal duration will be a trapezoid.
- Convolution of two rectangular pulses of equal duration will be a triangle.

Consider the signals $x_1(t)$ with amplitude $A_1$ and duration $T_1$, and $x_2(t)$ with amplitude $A_2$ and duration $T_2$.
![[conshort.png]]
We see that
$$ T_1 \neq T_2, \hspace{20pt} T_2 > T_1$$
The resulting signal $x_1(t) * x_2(t) = y(t)$ will have the duration $T_1 + T_2$. The height of the trapezoid is $A_1 A_2 T_1$. We multiply with $T_1$ since it is smaller. The starting point of the trapezoid is obtained from the property of extension. The first edge of the trapezoid is at $T_1$ since $T_1$ is smaller. The last edge of the trapezoid is at $T_2$ since it is larger. The resulting waveform is shown below. 
![[con_trap.png]]

## Example
---
We are interested in calculating $y(t)$. The waveforms are shown below
![[con1.png]]
We perform time reversal on the impulse response
![[time_rev.png]]
We perform time-shifting on the impulse response
![[time_shift.png]]
We will now perform multiplication and integration several times.
**Case 1, $t < 0$**
![[con2.png]]
We see that
$$ y(t) = 0$$
**Case 2, $0 < t < 1$**
![[con3.png]]
We see that as $h(t - \tau)$ moves into $x(t)$ the product is 1. The integral
$$ y(t) = \int_0^{t}1 d\tau = [\tau]_0^{t} = t $$
**Case 3, $1 < t < 2$**
![[con4.png]]
We see that the two signals are overlapping, and the product is 1.
$$ y(t) = \int_{t-1}^{t}1 d\tau = [\tau]_{t-1}^{t} = t - t + 1 = 1$$
**Case 4, $2 < t < 3$**
![[con5.png]]
We see that $h(t - \tau)$ is now moving out of $x(t)$.
$$ y(t) = \int_{t-1}^{2}1 d\tau = [\tau]_{t-1}^{2}= 2 - t + 1 = 3 - t$$
**Case 5, $t > 3$**
![[con6.png]]
We see that the product is 0.
$$ y(t) = 0$$
We can now write an expression for the output
$$ y(t) = 
\begin{cases}
0, \hspace{29pt} t < 0 \\
t, \hspace{30pt} 0 < t < 1 \\
1, \hspace{29pt} 1 < t < 2 \\
3 - t, \hspace{14pt} 2 < t < 3 \\
0, \hspace{31pt} t > 3 \\
\end{cases}
$$
We can plot the output
![[con_out.png]]
The expression can also be written as a sum of the unit ramp function
$$ y(t) = r(t) - r(t - 1) - r(t - 2) + r(t - 3)$$
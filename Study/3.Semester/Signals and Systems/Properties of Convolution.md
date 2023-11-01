## 1. Commutative Property
---
$$ x_1(t) * x_2(t) = x_2(t) * x_1(t)$$
## 2. Associative Property
---
$$ (x_1(t) * x_2(t)) * x_3(t) = x_1(t) * (x_2(t) * x_3(t))$$
## 3. Distributive Property
---
$$ x_1(t) * (x_2(t) + x_3(t)) = x_1(t) * x_2(t) + x_1(t) * x_3(t) $$
## 4. Property of Delta Function
---
We know that the delta function is the impulse signal.
$$ x(t) * \delta(t - t_1) = x(t - t_1) $$
If $t_1 = 0$
$$ x(t) * \delta(t) = x(t)$$
If weight of $\delta(t)$ not 1
$$ x(t) * A\delta(t - t_1) = Ax(t - t_1) $$
## 5. Derivative Property
---
$$ \frac{dy(t)}{dt} = x(t) * \frac{dh(t)}{dt} = \frac{dx(t)}{dt} * h(t) $$
## 6. Step Response Property
---
$$ x(t) * u(t) = \int_{-\infty}^{t} x(\tau) d\tau $$
## 7. Time Delay Property
---
$$ x_1(t - t_1) * x_2(t - t_2) = y(t - (t_1 + t_2)) $$
## 8. Time Scaling Property
---
$$ x_1(at) * x_2(at) = \frac{1}{|a|} y(at) $$
## 9. Total Area Property
---
For the convolution
$$ x_1(t) * x_2(t) = y(t) $$
the area $A$ under $y(t)$ is equal to the product of the area $A_1$ under $x_1(t)$ and the area $A_2$ under $x_2(t)$.
$$ A = A_1 A_2$$
## 10. Duration/Extension Property
---
If we have signals in the time range
$$ x_1(t), \hspace{20pt} t_1 \leq t \leq t_2 $$
$$ x_2(t), \hspace{20pt} t_3 \leq t \leq t_4 $$
Then the output
$$ y(t), \hspace{20pt} t_1 + t_3 \leq t \leq t_2 + t_4 $$

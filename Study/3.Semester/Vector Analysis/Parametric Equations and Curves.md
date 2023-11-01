Back to index:
[[1. Index - Vector Analysis]]

# Parametric Equations and Curves
Usually we look at functions in the form $y = f(x)$ or $x = h(y)$. The problem is that not all curves or equations easily fall into this form. For instance the equation of a circle centered at the origin with radius $r$
$$ x^2 + y^2 = r^2 $$
It will never be possible to write down this equation as a single equation in one of the forms above. It is possible to solve for $x$ or $y$ 
$$ x = \pm \sqrt{ r^2 - x^2}, \hspace{10pt} y = \pm \sqrt{r^2 - y^2} $$
But there are two functions for both $x$ and $y$. Each formula gives only a portion of the circle. To solve this problem we introduce parametric equations. Instead of defining $y$ in terms of $x$ and defining $x$ in terms of $y$, we define both $x$ and $y$ in terms of a third variable called a parameter
$$ x = f(t), \hspace{10pt} y = g(t) $$
Each value of $t$ defines a point $(x, y) = (f(t), g(t))$. By letting $t$ be all possible values we get the graph of the parametric eqautions called the parametric curve. A parametric curve has a direction fo motion given by increasing $t$. 
## Plot of Parametric Curve
A parametric curve can be plotted using Python
```python
import numpy as np
import matplotlib.pyplot as plt

t = np.linspace(-10, 10, 100)
x = t**2 + t
y = 2*t - 1

plt.figure(dpi = 100)
plt.plot(x, y)
```
![[parametric_curve.png]]
## Elimination of Parameter
The parameter of a set of parametric equations can often be eliminated to get an algebraic expression for $x,y$.  One of the easiest ways to elimate the parameter is to solve one of the equations for the parameter $t$ and then substitute that into the other equation.

The equation involving only $x$ and $y$ will NOT give the direction of motion of the curve.  
## Direction of Motion
The direction of motion can be determined by taking the derivatives of the parametric equations for instance
$$ x = t^2 + t, \hspace{10pt} y = 2t - 1 $$
$$ \frac{dx}{dt} = 2t + 1, \hspace{10pt} \frac{dy}{dt} = 2 $$
So as $t$ increases from negative to positive the motion in the x-direction changes from negative to positive, while the motion in the y-direction is constant. 
## Common Parametric Curves
| Curve                                                                | Parametric Equations                                                                                                                                                                                                                      |
| -------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ellipse <br/> $\frac{x^2}{a^2}+ \frac{y^2}{b^2} = 1$                 | Clockwise: <br/> $x = a \cos(t), \hspace{5pt} y = -b \sin(t)$ <br/> $0 \leq t \leq 2\pi$ <br/> Counter-Clockwise <br/> $x = a \cos(t), \hspace{5pt} y = b \sin(t)$ <br/> $0 \leq t \leq 2\pi$                                             |
| Circle <br/> $x^2 + y^2 = r^2$                                       | Clockwise: <br/> $x = r \cos(t), \hspace{5pt} y = -r \sin(t)$ <br/> $0 \leq t \leq 2\pi$ <br/> Counter-Clockwise: <br/> $x = r \cos(t), \hspace{5pt} y = r \sin(t)$ <br/> $0 \leq t \leq 2\pi$                                            |
| Line Segment From <br/> $(x_0, y_0, z_0)$ to <br/> $(x_1, y_1, z_1)$ | $\vec{r}(t) = (1 - t) \langle x_0, y_0, z_0 \rangle + t \langle x_1, y_1, z_1 \rangle$ <br/> $0 \leq t \leq 1$ <br/> or <br/> $x = (1 - t)x_0 + tx_1$ <br/> $y = (1 - t)y_0 + ty_1$ <br/> $z = (1 - t)z_0 + tz_1$ <br/> $0 \leq t \leq 1$ |

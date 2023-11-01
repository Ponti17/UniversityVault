Back to Index:
[[1. Index - Vector Analysis]]

# Surface Integrals

For some surface $S$
![[surface_integrals_graphic.png]]
The surface $S$ will lie above some region $D$.  For a surface $S$ given by $z = g(x,y)$, the surface integral is
$$ \iint \limits_S f(x,y,z)\, dS = \iint \limits_D f(x,y,g(x,y)) \sqrt{ \left( \frac{\partial g}{\partial x} \right)^2 + \left( \frac{\partial g}{\partial y} \right)^2 + 1 }\, dA $$
For a surface given by the parameterization
$$ \vec{r}(u,v) = x(u,v) \vec{i} + y(u,v) \vec{j} + z(u,v) \vec{k} $$
the surface integral is
$$ \iint \limits_S f(x,y,z)\, dS = \iint \limits_D f(\vec{r}(u,v)) | \vec{r}_u \times \vec{r}_v|\, dA$$
for surface given by $z = g(x,y)$ the parametization
$$ \vec{r}(x,y) = x\vec{i} + y\vec{j} + g(x,y)\vec{k} $$
where
$$ | \vec{r}_x \times \vec{r}_y | = \sqrt{ \left( \frac{\partial g}{\partial x} \right)^2 + \left( \frac{\partial g}{\partial y} \right)^2 + 1 } $$

## Example 1

Consider the integral
$$ \iint \limits_D 6xy\, dS $$
where $S$ is the portion of the plane $x + y + z = 1$ that lies in the first octant and is in front of the $yz$-plane. Since we are looking for the portion of the plane that lies in front of the $yz$-plane we wrtie the equation of the surface in the form $x = g(y,z)$. 
$$ x = 1 - y - z $$
A sketch of the surface
![[surface_integral_example1.png]]
And a sketch of the region $D$
![[surface_integral_example1_1.png]]
We get the equation for the hypotenuse by setting $x = 0$ in the equation for the plane, and solving for $z$. The ranges
$$ 0 \leq y \leq 1, \hspace{20pt} 0 \leq z \leq 1 - y $$
We arrive at the integral
$$ \iint \limits_S f(x,y,z)\, dS = \iint \limits_D f(g(y,z),y,z)  \sqrt{ \left( \frac{\partial g}{\partial y} \right)^2 + \left( \frac{\partial g}{\partial z} \right)^2 + 1 }\,dA $$
Let's do the integral. We plug in the expression for $x$ into the function in the surface integral
$$ \iint \limits_D 6xy\, dS = \iint \limits_D 6 ( 1 - y - z ) y \sqrt{1 + (-1)^2 + (-1)^2}\, dA $$
We now have a fairly simple double integral
$$ \iint \limits_S 6xy \, dS = \sqrt{3} \iint \limits_D 6(y - y^2 - zy) dA = 6 \sqrt{3} \int_0^1 \int_0^{1-y} y - y^2 - zy \, dz \, dy $$


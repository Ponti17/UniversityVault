rBack to index:
[[1. Index - Vector Analysis]]

# Surface Integrals Of Vector Fields
---

## Orientation of Surfaces
Just as the orientation of the curve for a line integral could change the answer, the same holds true for surface integrals. So a surface will have a certain **orientation**. If we consider a surface that has two sides that has a tangent plane at every point. Then the surface will at every point have two unit normal vector $\vec{n}_1$ and $\vec{n}_2 = -\vec{n}_1$. So every surface has two sets of normal vectors. The set that we choose gives the surface an orientation.

For a closed surface $S$, that encloses a region $E$, the orientation is **positive** if we choose the set of normal vectors that point outward from the region $E$, and **negative** if we choose the set of normal vectors that point in towards the region $E$.

## Determination of Unit Normal Vectors
Before we can work with surface integrals of vector fields we need to write a formula for unit normal vector corresponding to the specific orientation. Suppose a function is given by $z = g(x,y)$. We define a new function
$$ f(x,y,z) = z - g(x,y) $$
The surface is then given by $f(x,y,z) = 0$. The gradient vector $\nabla f$ will be orthogonal to the surface $f(x,y,z) = 0$. Now we just turn this into a unit vector
$$ \vec{n} = \frac{\nabla f}{ | \nabla f | } $$
For the function $f(x,y,z) = z - g(x,y)$ we get
$$ \vec{n} = \frac{ -g_x \vec{i} - g_y \vec{j} + \vec{k} }{ \sqrt{ (g_x)^2 + (g_y)^2 + 1 } } $$
From a notational standpoint, this is fairly convoluted. But we can see that the component of the normal vector in the $z$-direction is always positive. So this normal vector will always point upwards, though not necessarily directly up. This is important if we are working with a closed surface and we want the positive orientation. If it turns out we need the downward orientation we can just take the negative of this unit vector. 

## Unit Normal Vectors of Parametric Surfaces
If a surface is given parametrically as
$$ \vec{r}(u,v) = x(u,v) \vec{i} + y(u,v) \vec{j} + z(u,v) \vec{k} $$
then the vector $\vec{r}_u \times \vec{r}_v$ will be normal to the tangent plane at a particular point. In order to guarantee that it is a unit normal vector we say
$$ \vec{n} = \frac{ \vec{r}_u \times \vec{r}_v }{ | \vec{r}_u \times \vec{r}_v | } $$

## Evaluation of Surface Integrals of Vector Fields (Flux)
Given a vector field $\vec{F}$ with unit normal vector $\vec{n}$ then the surface integral of $\vec{F}$ over the surface $S$ is given by
$$ \iint \limits_S \vec{F} \cdot d\vec{S} = \iint \limits_S \vec{F} \cdot \vec{n} \, dS $$
where the right hand integral is a standard surface integral. This is called the flux of $\vec{F}$ across $S$. Let's assume that a surface is given by $z = g(x,y)$ and a vector field is given by $\vec{F} = P \vec{i} + Q \vec{j} + R \vec{k}$, and we want a upwards orientation. The surface integral
$$ \iint \limits_S \vec{F} \cdot d\vec{S} = \iint \limits_S \vec{F} \cdot \vec{n} \, dS = \iint \limits_D (P \vec{i} + Q \vec{j} + R \vec{k}) \cdot \left( \frac{ -g_x \vec{i} - g_y \vec{j} + \vec{k} }{ \sqrt{ (g_x)^2 + (g_y)^2 + 1 } } \right) \sqrt{ (g_x)^2 + (g_y)^2 + 1 } dA $$
$$ = \iint \limits_D (P \vec{i} + Q \vec{j} + R \vec{k}) \cdot (-g_x \vec{i} - g_y \vec{j} + \vec{k}) dA = \iint \limits_D -P g_x - Q g_y + R \, dA $$
We note here that we assumed an upwards orientation. If we needed the downward orientation then we would change the signs on the normal vector. We also notice that the messy square root of the unit normal vector always drops out. The surface integral when the surface is given parametrically
$$ \iint \limits_D \vec{F} \cdot d\vec{S} = \iint \limits_S \vec{F} \cdot \vec{n} \, dS = \iint \limits_D \vec{F} \cdot \left( \frac{ \vec{r}_u \times \vec{r}_v }{ | \vec{r}_u \times \vec{r}_v | } \right) | \vec{r}_u \times \vec{r}_v | dA = \iint \limits_D \vec{F} \cdot ( \vec{r}_u \times \vec{r}_v ) dA $$
Again we note that we may have to change the sign of $\vec{r}_u \times \vec{r}_v$ to match the orientation. 

## Example, Evaluation of Surface Integral of Semi-Sphere
We want to evaluate
$$ \iint \limits_S \vec{F} \cdot d\vec{S} $$
where $\vec{F} = x \vec{i} + y \vec{j} + z^4 \vec{k}$ and $S$ is the upper half of the sphere $x^2 + y^2 + z^2 = 9$ and the disk $x^2 + y^2 \leq 9$ in the plane $z = 0$. We assume that $S$ has the positive orientation.



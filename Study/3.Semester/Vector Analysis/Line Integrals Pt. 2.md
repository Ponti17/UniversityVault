Back to index:
[[1. Index - Vector Analysis]]

# Line Integrals Pt. 2

**This chapter concerns line integral with respect to $x$ and/or $y$ as well as line integrals of vector fields.
**
## Line Integrals With Respect to $x$ and $y$

We assume a two-dimensional curve $C$ with parameterization
$$ x = x(t), \hspace{5pt} y = y(t), \hspace{5pt} a \leq t \leq b $$
The line integral of $f$ with respect to $x$ is
$$ \int_C f(x,y) dx = \int_a^b f(x(t), y(t)) x'(t) dt $$
The line integral of $f$ with respect to $y$ is
$$ \int_C f(x,y) dy = \int_a^b f(x(t), y(t)) y'(t) dt $$
These two integrals often appear together so we have the following notation
$$ \int_C P\, dx + Q\, dy = \int_C P(x,y) dx + \int_C Q(x,y) dy $$

### Example, Line Integral With Respect to $x$ and $y$

We want to evaluate the following integral
$$ \int_C \sin(\pi y) dy + yx^2 dx $$
where $C$ is the line segment from $(0,2)$ to $(1,4)$. The parameterization of the curve
$$ \vec{r}(t) = (1 - t) \langle 0,2 \rangle + t \langle 1,4 \rangle = \langle t , 2 + 2t \rangle, \hspace{5pt} 0 \leq t \leq 1 $$
The line integral is
$$ \int_C \sin(\pi y) dy + yx^2 dx = \int_C \sin(\pi y) dy + \int_C yx^2 dx = \int_0^1 \sin(\pi(2 + 2t)) 2 dt + \int_0^1 (2 + 2t)t^2 dt $$

### Direction of Line Integral With Respect to $x$ and $y$

For line integrals with respect to $x$ and/or $y$ it is a fact that if $C$ is any curve then
$$ \int_{-C} f(x,y) dx = - \int_C f(x,y) dx \hspace{5pt} \textrm{and} \hspace{5pt} \int_{-C} f(x,y) dy = - \int_C f(x,y) dy $$
In the combined form
$$ \int_{-C} P\, dx + Q\, dy = - \int_C P\, dx + Q\, dy $$

## Line Integrals of Vector Fields

If we have the vector field
$$ \vec{F}(x,y,z) = P(x,y,z) \vec{i} + Q(x,y,z) \vec{j} + R(x,y,z) \vec{k} $$
and the three-dimensional smooth curve
$$ \vec{r}(t) = x(t) \vec{i} + y(t) \vec{j} + z(t) \vec{k}, \hspace{5pt} a \leq t \leq b $$
The line integral of $\vec{F}$ along $C$ is
$$ \int_C \vec{F} \cdot d\vec{r} = \int_a^b \vec{F}(\vec{r}(t)) \cdot \vec{r} \hspace{2pt}'(t) dt$$
Yes we are really talking about a dot product. Also $\vec{F}(\vec{r}(t))$ is shorthand for
$$ \vec{F}(\vec{r}(t)) = \vec{F}(x(t), y(t), z(t)) $$
Line integrals can also be written as a line integral with respect to arc length
$$ \int_C \vec{F} \cdot d\vec{r} = \int_C \vec{F} \cdot \vec{T} ds $$
where $\vec{T}(t)$ is the unit tangent vector
$$ \vec{T}(t) = \frac{\vec{r} \hspace{2pt} ' (t)}{| \vec{r} \hspace{2pt} ' (t) |} $$

### Example, Line Integral of Vector Field

We want to evaluate the integral
$$ \int_C \vec{F} \cdot d\vec{r} $$
where $\vec{F}(x,y,z) = 8x^2 y z \vec{i} + 5z \vec{j} - 4xy \vec{k}$ and $C$ is the curve given by $\vec{r}(t) = t\vec{i} + t^2 \vec{j} + t^3 \vec{k}, \hspace{5pt} 0 \leq t \leq 1$.  First we need the vector field evaluated along the curve
$$ \vec{F}(\vec{r}(t)) = 8t^2 (t^2) (t^3) \vec{i} + 5t^3 \vec{j} - 4t (t^2) \vec{k} = 8t^7 \vec{i} + 5t^3 \vec{j} - 4t^3 \vec{k} $$
The derivative of the parameterization
$$ \vec{r} \hspace{2pt}' (t) = \vec{i} + 2t \vec{j} + 3t^2 \vec{k} $$
The dot product
$$ \vec{F}(\vec{r}(t)) \cdot \vec{r} \hspace{2pt} ' (t) = 8t^7 + 10t^4 - 12t^5 $$
The line integral is then
$$ \int_C \vec{F} \cdot d \vec{r} = \int_0^1 8t^7 + 10t^4 -12t^5 dt $$

## Line Integrals of Vector Fields With Respect to $x$ and/or $y$

Given the vector field $\vec{F}(x,y,z) = P \vec{i} + Q \vec{j} + R \vec{k}$ and the curve $C$ parameterized by $\vec{r}(t) = x(t) \vec{i} + y(t) \vec{j} + z(t) \vec{k}, \hspace{5pt} a \leq t \leq b$ the line integral is
$$ \int_C \vec{F} \cdot d \vec{r} = \int_C P\, dx + Q\, dy + R\, dz $$
This also means that
$$ \int_{-C} \vec{F} \cdot d \vec{r} = - \int_C \vec{F} \cdot d\vec{r} $$

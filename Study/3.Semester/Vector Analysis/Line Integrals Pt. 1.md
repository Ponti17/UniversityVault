Back to index:
[[1. Index - Vector Analysis]]

# Line Integrals Pt. 1

**This chapter concerns only the line integral with respect to the arc lenght.**

In basic Calculus we integrated a function $f(x)$ depending on a single variable, over an interval $[a, b]$. In this case we were thinking of $x$ as taking all values in this interval starting at $a$ and ending at $b$. With line integrals we integrate a function $f(x,y)$ depending on two variables. The values of $x$ and $y$ will be the points $(x,y)$ that lie on a curve $C$. 

The curve $C$ is given by the parametric equations
$$ x = h(t), \hspace{5pt} y = g(t), \hspace{5pt} a \leq t \leq b $$
Often we will want to write the parameterization of the curve as a vector function
$$ \vec{r} (t) = h(t) \vec{i} + g(t) \vec{j}, \hspace{5pt} a \leq t \leq b $$
The curve is called **smooth** if $\vec{r}(t)$ is continous and $\vec{r}'(t) \neq 0$ for all $t$. The line integral of $f(x,y)$ along $C$ is denoted by
$$ \int_C f(x,y) ds $$
We use $ds$ to signify that we're moving along the curve $C$, instead of e.g. the x-axis (denoted by $dx$). Because of the $ds$ this is sometimes called the line integral of $f$ with respect to the arc length of $C$. To compute a line integral we will convert everything to parametric equations
$$ \int_C f(x,y) ds = \int_a^b f(h(t), g(t)) \sqrt{ \left( \frac{dx}{dt} \right)^2 + \left( \frac{dy}{dt} \right)^2 } dt $$
If we use the vector form of the parameterization then
$$ \int_C f(x,y) ds = \int_a^b f(h(t), g(t)) \hspace{2pt} | \vec{r} (t) | \hspace{2pt} dt $$

## Example, Line Integral of Half Circle

We want to evaluate the following integral
$$ \int_C xy^4 ds $$
Where $C$ is the right half of the circle $x^2 + y^2 = 16$ traced out in a counter clockwise direction. First we parameterize the circle
$$ x = 4 \cos(t), \hspace{5pt} y = 4 \sin(t) $$
The range of $t$'s that will give the right half of the circle is
$$ - \frac{\pi}{2} \leq t \leq \frac{\pi}{2} $$
The derivatives of the parametric equations
$$ \frac{dx}{dt} = - 4 \sin(t), \hspace{5pt} \frac{dy}{dt} = 4 \cos(t) $$
So ($\sin^2(t) + \cos^2(t) = 1$)
$$ ds = \sqrt{16 \sin^2 (t) + 16 \cos^2 (t)} dt = 4 dt $$
The line integral is then
$$ \int_C xy^4 ds = \int_{-\pi/2}^{\pi/2} 4 * 4 \cos(t) ( 4 \sin (t) )^4 dt = 4096 \int_{-\pi/2}^{\pi/2} \cos(t) \sin^4(t) dt$$

## Line Integrals of Piecewise Smooth Curves

A piecewise smooth curve is any curve that can be written as a finite sum of smooth curves $C_1, \ldots , C_n$, where the end point of $C_i$ is the starting point of $C_{i+1}$. To evalue this you simply sum of the line integrals of each piecewise curve
$$ \int_C f(x,y) ds = \int_{C_1} f(x,y) ds + \ldots + \int_{C_n} f(x,y) ds $$

## Direction of Line Integrals With Respect to Arc Lenght

Suppose that the curve $C$ has the parameterization $x = h(t)$ and $y = g(t)$. We also assume that the initial point on the curve is $A$ and the final point is $B$. The parameterization will determine an orientation for the curve where the positive direction is the direction that is traced out as $t$ increases. If we now let $-C$ be the curve with same points as $C$ but with the initial point and the final point swapped.  So $-C$ is the same curve as $C$ except the direction is opposite. The following is then true for the line integral with respect to the arc length
$$ \int_C f(x,y) ds = \int_{-C} f(x,y) ds $$

## Line Integrals of Three-Dimensional Curves

If we assume that the three-dimensional curve $C$ is given by the parameterization
$$ x = x(t), \hspace{5pt} y = y(t), \hspace{5pt} z = z(t), \hspace{5pt} a \leq t \leq b $$
then the line integral is given by
$$ \int_C f(x,y,z) ds = \int_a^b f(x(t), y(t), z(y)) \sqrt{ \left( \frac{dx}{dt} \right)^2 + \left( \frac{dy}{dt} \right)^2 + \left( \frac{dz}{dt} \right)^2} dt $$
Again the parameterization can be given as a vector function
$$ \vec{r}(t) = \langle x(t), y(t), z(t) \rangle $$
As with two-dimensional curves we have
$$ \sqrt{ \left( \frac{dx}{dt} \right)^2 + \left( \frac{dy}{dt} \right)^2 + \left( \frac{dz}{dt} \right)^2} = | \vec{r}'(t)| $$
So the line integral can also be written as
$$ \int_C f(x,y,z) ds = \int_a^b f(x(t), y(t), z(t)) \hspace{2pt} |\vec{r}'(t)| \hspace{2pt} dt $$

## Example, Line Integral of Helix Curve

We want to evaluate the following integral
$$ \int_C xyz\, ds $$
where $C$ is the helix given by
$$ \vec{r}(t) = \langle \cos(t), \sin(t), 3t \rangle, \hspace{5pt} 0 \leq t \leq 4 \pi $$
The line integral is
$$ \int_C xyz\, ds = \int_0^{4\pi} 3t \cos(t) \sin(t) \sqrt{ \sin^2(t) + \cos^2(t) + 9} dt $$

Back to index:
[[1. Index - Vector Analysis]]

# Parametric Surfaces
When we parameterized a curve we took values of $t$ from some interval $[a,b]$ and plugged them into
$$ \vec{r}(t) = x(t) \vec{i} + y(t) \vec{j} + z(t) \vec{k} $$
where the resulting vectors will be position vectors for points on the curve. For surfaces we will take points $(u,v)$ out of some two-dimensional space $D$ and plug them into
$$ \vec{r}(u, v) = x(u,v) \vec{i} + y(u,v) \vec{j} + z(u,v) \vec{k} $$
and the resulting vectors will be position vectors for the points on the surface $S$ we are parameterizing.

## Example, Parametric Representations For Surfaces
For the surface $x = 5y^2 + 2z^2 - 10$ we see that it is in the form $x = f(y,z)$. The set of parametric equations is then
$$ x = 5y^2 + 2z^2 - 10, \hspace{10pt} y = y, \hspace{10pt} z = z $$
The parametric representation
$$ \vec{r}(y,z) = (5y^2 + 2z^2 - 10) \vec{i} + y \vec{j} + z \vec{k} $$


## Parametrization of Surface Functions
$$ z = f(x,y) \hspace{10pt} \Rightarrow \hspace{10pt} \vec{r}(x,y) = x \vec{i} + y \vec{j} + f(x,y) \vec{k} $$
$$ x = f(y,z) \hspace{10pt} \Rightarrow \hspace{10pt} \vec{r}(x,y) = f(y,z) \vec{i} + y \vec{j} + z \vec{k} $$
$$ y = f(x,z) \hspace{10pt} \Rightarrow \hspace{10pt} \vec{r}(x,y) = x \vec{i} + f(x,z) \vec{j} + z \vec{k} $$

## Tangent Plane to Parametric Surface
We want to find the tangent plane to the parametric surface $S$
$$ \vec{r}(u, v) = x(u,v) \vec{i} + y(u,v) \vec{j} + z(u,v) \vec{k} $$

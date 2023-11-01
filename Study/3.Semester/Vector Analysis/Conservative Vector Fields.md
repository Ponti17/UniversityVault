Back to index:
[[1. Index - Vector Analysis]]

# Conservative Vector Fields

## Two-dimensional Vector Fields

For two dimensional vector fields, it is easy to determine if the vector field is conservative. 

Let $\vec{F} = P \vec{i} + Q \vec{j}$ be a vector field on an open and simply-connected region $D$. Then if the partial derivatives of $P$ and $Q$ are continous in $D$ and
$$ \frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x} $$
the vector field $\vec{F}$ is conservative. If we assume a vector field $\vec{F}$ is conservative then we know that a potential function $f(x,y)$ exists. We can write
$$ \nabla f = \frac{\partial f}{\partial x} \vec{i} + \frac{\partial f}{\partial y} \vec{j} = P \vec{i} + Q \vec{j} = \vec{F} $$
which gives us that
$$ \frac{\partial f}{\partial x} = P, \hspace{20pt} \frac{\partial f}{\partial y} = Q $$
so we arrive at the following two equations for the potential function
$$ f(x, y) = \int P(x,y) dx \hspace{20pt} \textrm{or} \hspace{20pt}  f(x,y) = \int Q(x,y) dy $$

## Three-dimensional Vector Fields

If given a three-dimensional conservative vector field we can determine a potential function by using the fact that
$$ \nabla f = \frac{\partial f}{\partial x} \vec{i} + \frac{\partial f}{\partial y} \vec{j} + \frac{\partial f}{\partial z} \vec{k} = P \vec{i} + Q \vec{j} + R \vec{k} = \vec{F} $$

### Example, Determination of potential function for three-dimensional vector field.

Consider the vector field
$$ \vec{F} = 2xy^3 z^4 \vec{i} + 3x^2 y^2 z^4 \vec{j} + 4x^2 y^3 z^3 \vec{k} $$
So we have
$$ \frac{\partial f}{\partial x} = 2xy^3 z^4, \hspace{10pt} \frac{\partial f}{\partial y} = 3x^2y^2z^4, \hspace{10pt} \frac{\partial f}{\partial z} = 4x^2y^3z^3, \hspace{10pt} $$
We can integrate the first one with respect to $x$, the second one with respect to $y$ or the third one with respect to $z$. In this case lets integrate the first one with respect to $x$
$$ f(x,y,z) = \int 2xy^3z^4 dx = x^2y^3z^4 + g(y,z) $$
New we can take the derivative of this with respect to $y$ and set it equal to $Q$
$$ \frac{\partial f}{\partial y} = 3x^2 y^2 z^4 + \frac{\partial}{\partial y}g(y,z) = 3x^2 y^2 z^4 = Q$$

Since the derivative of $g(y,z)$ with respect to $y$ gives zero, $g(y,z)$ could at most be a function of $z$. So the potential function must be of the form
$$ f(x,y,z) = x^2 y^3 z^4 + h(z) $$
We new take the derivative with respect to $z$ and set the result equal $R$
$$ \frac{\partial f}{\partial z} = 4x^2 y^3 z^3 + \frac{\partial}{\partial z}h(z) = 4x^2 y^3 z^3 = R $$
So
$$ \frac{\partial}{\partial z}h(z) = 0 \Rightarrow h(z) = C $$
The potential function is then
$$ f(x,y,z) = x^2y^3z^4 + C $$


Back to index:
[[1. Index - Vector Analysis]]

# Vector Fields
A vector field on two (or three) dimensional space is a function $\vec{F}$ that assigns to each point $(x, y)$ (or $(x, y, z)$) a two (or three dimensional) vector given by $\vec{F} (x, y)$ (or $\vec{F}(x, y, z)$). The standard notation for a vector field in $\mathbb{R}^3$ 
$$ \vec{F} = P(x, y, z) \vec{i} + Q(x,y, z) \vec{j} + R(x, y, z) \vec{k} $$
The function $P, Q, R$ are sometimes called scalar functions. 
## Sketch of Vector Field
We want to sketch the vector field $\vec{F} (x, y)  = -y \vec{i} + x \vec{j}$. To graph the the vector field we need to get some values. We plug some points into the function
$$ \vec{F} (2, 2) = -2 \vec{i} + 2 \vec{j} $$
$$ \vec{F} (2, -2) = 2 \vec{i} + 2 \vec{j} $$
These calculations tell us that at the point $(2, 2)$ we will plot the vector $-2 \vec{i} + 2 \vec{j}$. Alternatively the vector field can be plotted in python
```python
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline

x,y = np.meshgrid(np.linspace(-10,10,15),np.linspace(-10,10,15))

u = -y
v = x

plt.figure(dpi = 200)
plt.gca().set_aspect('equal', adjustable='box')
plt.quiver(x,y,u,v)
plt.show()
```
![[vector_field.png]]
## Gradient Vector Field
For a given function $f(x, y, z)$ the gradient vector is defined by
$$ \nabla f = \langle f_x, f_y, f_z \rangle $$
The result is a vector field often called the gradient vector field. The function $f(x, y, z)$ is often called a scalar function to differentiate it from the vector field. As an example the gradient vector field of the function
$$ f(x, y) = x^2 \sin(5y) $$
$$ \nabla f = \langle 2x \sin(5y), 5x^2 \cos(5y) \rangle $$

## Conservative Vector Fields
A vector field $\vec{F}$ is called a conservative vector field if there exists a function $f$ such that $\vec{F} = \nabla f$. If $\vec{F}$ is a conservative vector field then the function $f$ is called a potential function for $\vec{F}$. 

This means that a vector field is conservative if it is also a gradient vector field for some function.  

For example the vector field $\vec{F} = y \vec{i} + x \vec{j}$ is a conservative vector field
with a potential function of $f(x, y) = xy$ because $\nabla f = \langle y, x \rangle$. 

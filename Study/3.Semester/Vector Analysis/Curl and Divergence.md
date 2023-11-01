Back to index:
[[1. Index - Vector Analysis]]

# Curl

Given the vector field $\vec{F} = P \vec{i} + Q \vec{j} + R \vec{k}$ the curl is defined as
$$ \textrm{curl } \vec{F} = (R_y - Q_z) \vec{i} + (P_z - R_x) \vec{j} + (Q_x - P_y) \vec{k} $$
Curl has another (easier) definition using the $\nabla$ operator
$$ \nabla = \frac{\partial}{\partial x} \vec{i} + \frac{\partial}{\partial y} \vec{j} + \frac{\partial}{\partial z} \vec{k} $$
We use this as if it's a function
$$ \nabla f = \frac{\partial f}{\partial x} \vec{i} + \frac{\partial f}{\partial y} \vec{j} + \frac{\partial f}{\partial z} \vec{k} $$
Using $\nabla$ curl can be defined as the cross product
$$ \textrm{curl } \vec{F} = \nabla \times \vec{F} = \begin{bmatrix} \vec{i} & \vec{j} & \vec{k} \\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ P & Q & R \end{bmatrix} $$
There a couple of facts that use the curl of a vector field
- If $f(x,y,z)$ has continous second order partial derivatives then $\textrm{curl}(\nabla f) = \vec{0}$. 
- If $\vec{F}$ is a conservative vector field then $\textrm{curl } \vec{F} = \vec{0}$.
- If $\vec{F}$ is defined on all of $\mathbb{R}^3$ whose components have continous first order partial derivative and $\textrm{curl } \vec{F} = \vec{0}$ then $\vec{F}$ is a conservative vector field.
- 
## Interpretation of Curl

The curl of a vector field captures the idea of how a fluid may rotate. Imagine that the vector field $\vec{F}$ below represents fluid flow.
![[curl_field_1.png]]
The curl represents the "microscopic circulation".  Imagine that we submerse a smal sphere into the fluid flow, and we fix the center of the sphere at some point so the sphere cannot follow the fluid around. The rotation of such a sphere measures the curl of the vector field at the point in the center of the sphere. 
![[curl_field_2.png]]
The curl of $\vec{F}$ is a vector that points along the axis of rotation and whose length corresponds to the speed of rotation. The direction of the curl vector abides the "right hand rule". If we curl our fingers of our right hand in the direction the sphere is rotation, our thumb will point in the direction of the curl vector. 

# Divergence

Given the vector field $\vec{F} = Q \vec{i} + Q \vec{j} + R \vec{k}$ the divergence is defined to be
$$ \textrm{div } \vec{F} = \frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z} $$
there is also a definition in terms of the $\nabla$ operator
$$ \textrm{div } \vec{F} = \nabla \cdot \vec{F} $$
we also have the following relationship about the curl and the divergence
$$ \textrm{div} ( \textrm{curl } \vec{F}) = 0 $$

## Interpretation of Divergence

If we imagine a vector field $\vec{F}$ that represents the flow of fluid. The divergence gives us the expansion of the fluid.
![[vector_div_1.png]]
If we place a sphere at a point in the vector field it is obvious that the fluid is flowing out of the sphere, hence $\textrm{div } \vec{F} > 0$. 

# Laplace Operator

If we consider
$$ \textrm{div} (\nabla f) = \nabla \cdot \nabla f = f_{xx} + f_{yy} + f_{zz} $$
then the laplace operator is defined as
$$ \nabla^2 = \nabla \cdot \nabla $$
# Green's Theorem

There are two vector forms of Green's Theorem
$$ \oint_C \vec{F} \cdot d\vec{r} = \iint_D ( \textrm{curl } \vec{F }) \cdot \vec{k}\, dA $$
where $\vec{k}$ is the standard unit vector in the positive $z$ direciton. The second form uses the divergence. In this case we need the outward unit normal vector to the curve $C$. If $C$ is parameterized by
$$ \vec{r} = x(t) \vec{i} + y(t) \vec{j} $$
then the outward unit normal vector is
$$ \vec{n} = \frac{y'(t)}{| \vec{r} \hspace{2pt} ' (t) |} \vec{i} - \frac{x'(t)}{| \vec{r} \hspace{2pt} ' (t) |} \vec{j}  $$
The vector form of Green's theorem that uses the divergence is then
$$ \oint_C \vec{F} \cdot \vec{n} ds = \iint_D \textrm{div } \vec{F}\,dA $$

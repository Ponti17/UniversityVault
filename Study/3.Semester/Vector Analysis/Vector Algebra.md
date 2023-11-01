Back to index:
[[1. Index - Vector Analysis]]

# Vector Algebra
## Vector Addition
![[vector_addition.png]]
$$ \vec{v} + \vec{u} = \langle v_1 + u_1, v_2 + u_2 \rangle$$

## Vector Subtraction
![](vector_subtraction.png)
$$ \vec{v} - \vec{u} = \langle v_1 - u_1, v_2 - u_2 \rangle$$
## Vector Components
![[vector_components.png]]
A vector $a$ extends from the point $(x_1, y_1, z_1)$ to the point $(x_2, y_2, z_2)$. The components of the vector are the three number $a_1 = x_2 - x_1, \hspace{5pt} a_2 = y_2 - y_1,\hspace{5pt} a_3 = z_2 - z_1$. The vector can be written in the form $a = (a_1, a_2, a_3)$. If we introduce three unit vectors $e_1, e_2, e_3$ which point along the coodinate axes $x, y ,z$, the vector can also be written as $a = a_1 e_1 + a_2 e_2 + a_3 e_3$.  The sum of two vectors $a, b$ is $$a + b = a_1 e_1 + a_2 e_2 + a_3 e_3 + b_1 e_1 + b_2 e_2 + b_3 e_3 = (a_1 + b_1)e_1 + (a_2 + b_2)e_2 + (a_3 + b_3)e_3$$
## Vector Magnitude
The magnitude of a vector is written $|a|$ and can be calculated using Pythagoras's theorem $$ |a| = \sqrt{a_1^2 + a_2^2 + a_3^2}$$
## Position Vector
The position of a point in space $(x, y, z)$ defines a vector which points from the origin to the point $(x, y, z)$.  This vector is called the position vector of a point, and is usually denoted $r$, with components $r = (x, y, z)$. 

## Dot Product
The dot product of two vectors is a scalar quantity. It is written $a \cdot b$ and can be calculated as the product of the magnitudes and cosine to the angle $\theta$ between them
$$ a \cdot b = |a| |b| \cos{\theta} = a_x b_x + a_y b_y$$
If two vectors $a$ and $b$ are orthogonal then $a \cdot b = 0$. 

The dot product of a vector with itself $a \cdot a = |a|^2$. 

The quantity $|b| \cos \theta$ represents the component of vector $b$ in the direction of vector $a$. The dot product basically represents the magnitude of $a$ multiplied by the component of $b$ in the direction of $a$. 

## Cross Product
The cross product or vector product of two vectors is a vector quantity, written $a \times b$. The magnitude of $a \times b$ is $|a| |b| \sin \theta$ where $\theta$ is the angle between the two vectors. The magnitude of the cross product equals the area of a parallelogram with vector $a$ and $b$ for its sides. The direction of $a \times b$ is perpendicular to both $a$ and $b$. 

The cross product
- Zero when vector $a$ and $b$ point in the same or opposite directions.
- Reaches maximum length when vectors $a$ and $b$ are orthogonal. 

The cross product can be calculated by
$$ a \times b = |a| |b| \sin(\theta) n $$
where $n$ is the unit vector at right angles to both $a$ and $b$. The cross product is also
$$ a \times b = \langle c_x, c_y, c_z \rangle $$
where $c_x = a_y b_z - a_z b_y$, $c_y = a_z b_x - a_x b_z$, $c_z = a_x b_y - a_y - b_x$. 
![[right-hand-rule.jpg]]
The cross product can also be written as the determinant of a $3 \times 3$ matrix
$$ a \times b = \textrm{det}\begin{bmatrix} e_1 & e_2 & e_3 \\ a_1 & a_2 & a_3 \\ b_1 & b_2 & b_3 \end{bmatrix} $$

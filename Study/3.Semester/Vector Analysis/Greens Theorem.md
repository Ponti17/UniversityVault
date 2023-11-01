Back to index:
[[1. Index - Vector Analysis]]

# Green's Theorem

Let $C$ be a closed curve and $D$ be the region enclosed by the curve.
![[closed_curve_greens.png]]
The curve is **simple** and **closed**, so there are no holes in the region $D$. The direction is positive (anti-clockwise). Any $C$ has a positive orientation if the region it encloses is always on the left. Green's theorem states that

Let $C$ be a positively oriented, piecewise smooth, simple, closed curve and let $D$ be the region enclosed by the curve. If $P$ and $Q$ have continous first order partial derivatives on $D$ then
$$ \int_C Pdx + Qdy = \iint_D \left( \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} \right) dA $$
When working with a line integral in which the path satisfies Green's theorem the integral will often be denoted as
$$ \oint_C Pdx + Qdy $$

## Example, Green's Theorem

We want to evaluate the integral
$$ \oint_C y^3 dx - x^3 dy $$
where $C$ is the positively oriented circle of radius $2$ centered at the origin.  First we identify $P$ and $Q$
$$ P = y^3, \hspace{10pt} Q = -x^3 $$
Using Green's theorem we get
$$ \oint_C y^3 dx - x^3 dy = \iint_D -3x^2 - 3y^2 dA $$
where $D$ is a disk of radius 2 centered at the origin. Since we are dealing with a disk we use polar coordinates
$$ \oint_C y^3 dx - x^3 dy = -3 \iint_D (x^2 + y^2) dA = -3 \int_0^{2\pi} \int_0^2 r^3 dr\, d\theta $$




## Green's Theorem On Regions With Holes

Green's Theorem will not work on regions that have holes in them. However there is a way to deal with them. Consider the following region
![[greens_theorem_holes.png]]
This region doesn't have any holes, but is nonetheless a good example. The region $D$ will be $D_1 \cup D_2$. The boundary of $D_1$ is $C_1 \cup C_3$ and the boundary of $D_2$ is $C_2 \cup (-C_3)$. Notice that both of these boundaries are positively oriented. Note that we can think of the whole boundary, $C$, as
$$ C = (C_1 \cup C_3) \cup (C_2 \cup (-C_3)) = C_1 \cup C_2 $$
Let's start with the following double integral and break it up
$$ \iint_D (Q_x - P_y) dA = \iint_{D_1 \cup D_2} (Q_x - P_y) dA = \iint_{D_1} (Q_x - P_y) dA + \iint_{D_2} (Q_x - P_y) dA $$
Now we use Green's theorem on each of these and break them up further
$$ \iint_D (Q_x - P_y) dA = \iint_{D_1} (Q_x - P_y) dA + \iint_{D_2} (Q_x - P_y) dA $$
$$ = \oint_{C_1 \cup C_3} Pdx + Qdy + \oint_{C_2 \cup (-C_3)} Pdx + Qdy $$
$$ = \oint_{C_1} Pdx + Qdy + \oint_{C_3} Pdx + Qdy + \oint_{C_2} Pdx + Qdy + \oint_{-C_3} Pdx + Qdy $$
Now we recall that
$$ \oint_{-C_3} Pdx + Qdy = - \oint_{C_3} Pdx + Qdy $$
So we get
$$ \oint_{C_1} Pdx + Qdy + \oint_{C_3} Pdx + Qdy + \oint_{C_2} Pdx + Qdy + \oint_{-C_3} Pdx + Qdy $$
$$ = \oint_{C_1} Pdx + Qdy +\oint_{C_2} Pdx + Qdy $$
Combining this
$$ \oint_{C_1} Pdx + Qdy + \oint_{C_2} Pdx + Qdy = \oint_{C_1 \cup C_2} Pdx + Qdy = \oint_C Pdx + Qdy $$
So now we know that if we break up a region, then the line integral on the pieces of the curve that are in the middle of the region will cancel out. 

## Green's Theorem On Circle With Hole

Consider the ring
![[greens_theorem_ring.png]]
Both of the curves are positively oriented. Since this region has a hole it is at first not possible to use Green's theorem. However, if we cut the disk in half we get
![[greens_theorem_ring_cut.png]]
The boundary of $D_1$ is $C_1 \cup C_2 \cup C_5 \cup C_6$ and the boundary of $D_2$ is $C_3 \cup C_4 \cup (-C_5) \cup (-C_6)$. 
Back to index:
[[1. Index - Vector Analysis]]

# Stokes' Theorem
---
Stokes' Theorem relates a line integral to a surface integral. 

Consider the surface. Around the the edge there is a curve $C$ called the **boundary** curve. The orientation of the surface $S$ induces a positive orientation of $C$. 

![[StokesTheoremSurface.png]]

**Stokes' Theorem**
Let $S$ be an oriented smooth surface that is bounded by a simple, closed, smooth boundary curve $C$ with positive orientation. Also let $\vec{F}$ be a vector field then,
$$ \int \limits_C \vec{F} \cdot d\vec{r} = \iint \limits_S \textrm{curl} \vec{F} \cdot d\vec{S} $$
# Divergence Theorem
---
The divergence theorem relates a surface integral to a triple integral.

**Divergence Theorem**
Let $E$ be a simple solid region and $S$ is the boundary surface of $E$ with positive orientation. Let $\vec{F}$ be a vector field whose components have continuous first order partial derivatives. Then,
$$ \iint \limits_S \vec{F} \cdot d\vec{S} = \iiint \limits_E \textrm{div} \vec{F} \, dV $$

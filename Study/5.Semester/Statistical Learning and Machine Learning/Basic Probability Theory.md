# Probability Theory
Random variables are denoted as uppercase letters e.g. $X, Y$. The probability of a RV being some value $x$ is denoted as $p(X = x)$. 

The sum and product rule generalized
$$ p(X) = \sum_Y p(X, Y) $$
$$ p(X, Y) = p(Y|X)p(X) $$
## Sum Rule
The probability that $X$ will take the value $x_i$ and $Y$ will take the value $y_j$ is the **joint probability**
$$ p(X = x_i, Y = y_j) $$
The probability that $X = x_i$ irrespective of the value of $Y$ is written as $p(X = x_i)$ and is given by the **sum rule**
$$ p(X = x_i) = \sum_{j=1}^L p(X = x_i, Y = y_j) $$
The probability $p(X = x_i)$ is called the **marginal probability**. 
## Product Rule
If we only consider instances in which $X = x_i$, then the fraction of these instances where $Y = y_j$ is written $p(Y = y_j|X = x_i)$ and called the **conditional probability** of $Y = y_j$ given $X = x_i$. We have the following relationship called the **product rule**
$$ p(X = x_i, Y = y_j) = p(Y = y_j | X = x_i)p(X = x_i) $$
## Verbalization

**Joint probability**
The probability of $X$ and $Y$
$$ p(X, Y) $$
**Conditional probability**
The probability of $Y$ given $X$
$$ p(Y|X) $$
**Marginal probability**
The probability of $X$
$$ p(X) $$
## Bayes' Theorem
From the product rule, together with the symmetry property $p(X, Y) = p(Y, X)$, we have the following relationship 
$$ p(Y|X) = \frac{p(X|Y)p(Y)}{p(X)} $$
called Bayes' theorem. Using the sum rule, the denominator can be expressed as
$$ p(X) = \sum_Y p(X|Y)p(Y) $$
##
# Expectation
The average value of some function $f(x)$ under a probability distribution $p(x)$ is called the **expectation** of $f(x)$ and will be denoted by $\mathbb{E}[f]$. For a discrete distribution
$$ \mathbb{E}[f] = \sum_x p(x) f(x) $$
in the case of continuous variables
$$ \mathbb{E}[f] = \int p(x) f(x) dx $$
In either case, if we are given a finite number $N$ of points drawn from the probability distribution or probability density, then the expectation can be approximated as
$$ \mathbb{E}[f] \approx \frac{1}{N} \sum_{n=1}^N f(x_n) $$
where the above approximation becomes exact in the limit $N \to \infty$. In the case of multivariable functions, we indicate the variable being averaged
$$ \mathbb{E}_x[f(x,y)] $$
The expectation $\mathbb{E}_x[f(x,y)]$ will be a function of $y$. There is finally also the conditional expectation 
$$ \mathbb{E}_x [f|y] = \sum_x p(x|y)f(x) $$
# Variance
The variance of $f(x)$
$$ \text{var}[f] = \mathbb{E}[(f(x) - \mathbb{E}[f(x)])^2] = \mathbb{E}[f(x)^2] - \mathbb{E}[f(x)]^2 $$
and measures how much variability there is in $f(x)$ around its mean value $\mathbb{E}[f(x)]$. 

We can also consider the variance of the variable $x$ 
$$ \text{var}[x] = \mathbb{E}[x^2] - \mathbb{E}[x]^2 $$
# Covariance
For two random variables $x$ and $y$, the covariance is given by
$$ \text{cov}[x,y] = \mathbb{E}_{x,y}[xy] - \mathbb{E}[x] \mathbb{E}[y] $$
which expresses the extent to which $x$ and $y$ vary together. If $x$ and $y$ are **independent**, their covariance vanishes. 

In the case of two vectors of RV's the covariance is a matrix
$$ \text{cov}[\mathbf{x},\mathbf{y}] = \mathbb{E}_{x,y}[\mathbf{x}\mathbf{y}^T] - \mathbb{E}[\mathbf{x}]\mathbb{E}[\mathbf{y}^T] $$

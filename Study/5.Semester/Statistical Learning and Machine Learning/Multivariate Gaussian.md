# Multivariate Gaussian
The Gaussian distribution defined over a D-dimensional vector $\mathbf{x}$ of continuous variables
$$ \mathcal{N}(\mathbf{x}|\mathbf{\mu}, \mathbf{\Sigma}) = \frac{1}{(2\pi)^{D/2}|\mathbf{\Sigma}|^{1/2}} \exp \left\{ - \frac{1}{2} (\mathbf{x} - \mathbb{\mu})^T \mathbf{\Sigma}^{-1}(\mathbf{x} - \mathbf{\mu}) \right\} $$
where the D-dimensional vector $\mu$ is the mean, the $D\times D$ matrix $\Sigma$ is called the **covariance**, and $|\Sigma|$ denotes the **determinant** of $\Sigma$. 

If we have a dataset of observations $\mathbf{x} = (x_1,\ldots,x_N)^T$, representing $N$ observations of the scalar variable $x$. The observations are drawn independently from a Gaussian distribution $\mu$ and $\sigma^2$ we would like to determine. 

## Maximum Likelihood
Data points that are drawn independently from the same distribution are **independent and identically distributed**, which is abbreviated **i.i.d**. Since the data is i.i.d., the probability of the data set given $\mu$ and $\sigma^2$
$$ p(\mathbf{x}|\mu, \sigma^2) = \prod_{n=1}^N \mathcal{N}(x_n|\mu, \sigma^2) $$
also known as the likelihood function. When estimating values for unknown parameters we maximize the likelihood function. It is often easier to maximize the log
$$ \ln p(\mathbf{x}|\mu, \sigma^2) = -\frac{1}{2\sigma^2} (x_n - \mu)^2 - \frac{N}{2}\ln \sigma^2 - \frac{N}{2}\ln(2\pi) $$
Maximizing with respect to to $\mu$ and $\sigma^2$
$$ \mu_{ML} = \frac{1}{N} \sum_{n=1}^N x_n $$
$$ \sigma^2_{ML} = \frac{1}{N} \sum_{n=1}^N (x_n - \mu_{ML})^2 $$
## Bias
The maximum likelihood approach systematically underestimates the variance. This is an example of a phenomenon called bias. It is related to the problem of over-fitting. 
$$ \mathbb{E}[\mu_{ML}] = \mu $$
$$ \mathbb{E}[\sigma^2_{ML}] = \left( \frac{N-1}{N} \right)\sigma^2 $$
We see that on average the maximum likelihood estimate will obtain the correct mean, but will underestimate the variance be a factor $(N-1)/N$. 
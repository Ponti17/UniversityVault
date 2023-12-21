# Gaussian/Normal Distribution
For the case of a single real-valued variable $x$, the Gaussian distribution is defined by
$$ \mathcal{N}(x|\mu, \sigma^2) = \frac{1}{(2\pi\sigma^2)^{1/2}} \exp \left( - \frac{1}{2\sigma^2}(x - \mu)^2 \right) $$
where $\mu$ is the mean, and $\sigma^2$ is the variance. The square root of the variance $\sigma$ is called the standard deviation. The reciprocal of the variance $\beta = 1/\sigma^2$ is called the precision. The Gaussian distribution has the following properties
$$ \int_{-\infty}^\infty \mathcal{N}(x|\mu, \sigma^2) dx = 1 $$
$$ \mathbb{E}[x] = \int_{-\infty}^\infty \mathcal{N}(x|\mu, \sigma^2)x\,dx = \mu $$
$$  \mathbb{E}[x^2] = \int_{-\infty}^\infty \mathcal{N}(x|\mu, \sigma^2)x^2\,dx = \mu^2 + \sigma^2 $$
The variance
$$ \text{var}[x] = \mathbb{E}[x^2] - \mathbb{E}[x]^2 = \sigma^2 $$
The maximum of a distribution is called the mode. For the Gaussian distribution the mode is equal its mean.

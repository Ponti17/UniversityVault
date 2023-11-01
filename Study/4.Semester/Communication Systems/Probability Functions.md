## Standard Gaussian
For a gaussian of mean $\mu$ and variance $\sigma^2$
$$ P(Y > a) = \int_a^{\infty}\frac{1}{\sqrt{2\pi} \sigma} e^{ -  \frac{(y - \mu)^2}{2\sigma^2} } dy$$
![[gaussian.png]]

## Error Function
The error function is a gaussian with $\mu = 0$ and $\sigma = 1/\sqrt{2}$ 
$$ erf(z) = \frac{2}{\sqrt{\pi}} \int_0^{z}e^{-t^{2}}dt $$
We integrate from 0 to z and multiply with 2. The same as integrating from -z to z.
![[erf.png]]

## Q-function
The Q-function is a gaussian with $\mu = 0$ and $\sigma = 1$. 
$$ Q(x) = \frac{1}{\sqrt{2\pi}} \int_x^{\infty}e^{-\frac{u^2}{2} } du$$
The gaussian CDF with mean 0 and SD 1.
$$ F(x) = \frac{1}{\sigma \sqrt{2\pi}} \int_{-\infty}^x e^{-x^2 / 2} dx $$
The Q--function 
$$ Q(x) = 1 - F(x) $$
Tells us the probability that a zero-mean unit-variance gaussian random variable is greater than or equal to some number
$$ P(x \geq A) = Q(A) $$
For some other Gaussian random variable with mean $\mu$ and SD $\sigma$ the Q-function can still be used. For the probability of a random variable $X$ is larger than some number $x$ 
$$ P(X > x) = Q\left( \frac{x - \mu}{\sigma}\right) $$
For the probability that a random variable is less than $x$
$$P(X \leq x) = 1 - Q\left( \frac{x - \mu}{\sigma} \right) $$
The Q-function has the following relationship
$$ Q(x) = 1 - Q(-x) $$


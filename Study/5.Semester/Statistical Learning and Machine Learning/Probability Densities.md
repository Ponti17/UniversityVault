# Probability Densities
For continuous variables the probability $p(x)$ is called the probability density over $x$. The probability that $x$ will lie in an interval $(a,b)$ is given by the probability density function (PDF)
$$ p(x \in (a,b)) = \int_a^b p(x) dx $$
Probabilities are nonnegative and the value of $x$ must lie on the real axis the probability density $p(x)$ must satisfy
$$ p(x) \geq 0 $$
$$ \int_{-\infty}^\infty p(x) dx = 1 $$
The probability that $x$ lies in the interval $(-\infty, z)$ is given by the cumulative distribution function (CDF) 
$$ P(z) = \int_{-\infty}^z p(x) dx $$
which satisfies
$$ P'(x) = p(x) $$
![[Pasted image 20231214122700.png|500]]
The sum and product rules, as well as Bayes' theorem, apply to the case of probability densities. If $x$ and $y$ are two real variables, then the sum and product rules
$$ p(x) = \int p(x,y) dy $$
$$ p(x,y) = p(y|x)p(x) $$


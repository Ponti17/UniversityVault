ROC: Set of all values of $z$ for which the $z$ transform of a signal $x[n]$ converges (exists).

The z-transform is an infinite series. Only for some values of $z$ does this converges.
$$ X(z) = \sum\limits_{n=-\infty}^{\infty}x[n] z^{-n}$$
## Case 1: Delay
For the system
$$ w[n] = \delta[n - n_0]$$
which is a delayed impulse at $n_0$, the z-transform
$$ W(z) = \sum\limits_{n=-\infty}^{\infty}\delta[n - n_0] z^{-n} = z^{-n_0}$$
we see that for $n_0 > 0$, then $z=0$ is not defined as
$$ z^{^{-n_0}} = \frac{n_0}{z} $$
and that will result in division by zero. On the other hand if $n_0 < 0$ then $z = \infty$ is not defined as that will go towards infinity i.e. will not converge. So if $n_0 > 0$
$$ W(z) = z^{-n_0}, \textrm{ ROC: } z \neq 0 $$

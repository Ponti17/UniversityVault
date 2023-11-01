The moment of a function is defined as
$$ E[X] = \int_{-\infty}^\infty x P_X(x) dx $$
where $P_x$ is the PDF. The second moment and etc.
$$ E[X^2] = \int_{-\infty}^\infty x^2 P_X(x) dx $$
The moment generating function (MGF)
$$ M_X(t) = E[e^{tX}] = \int_{-\infty}^\infty e^{tX} P_X(x) dx = E[1 + tX + \frac{t^2X^2}{2!} + \frac{t^3X^3}{3!} + ...]$$
$$ = 1 + tE[X] + \frac{t^2}{2!}E[X^2] + \frac{t^3}{3!} E[X^3] $$
we see now that the function generates all the moments. To find a specific moment, take the derivative and set $t = 0$. The MGF for a Gaussian
$$ M_x(t) = e^{t\mu + (1/2) \sigma^2 t^2} $$
The first moment
$$ M_x'(t) = \mu e^{t\mu} e^{(1/2)\sigma^2 t^2} + e^{t\mu} \sigma^2 t e^{(1/2)\sigma^2 t^2} \Big|_{t=0} = \mu$$

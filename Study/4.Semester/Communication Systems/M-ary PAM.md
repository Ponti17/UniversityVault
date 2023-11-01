For $M = 8$ PAM we have the signal space diagram
![[sigspace.png]]
We assume equal probability for all symbols. The probability of symbol error
$$ P[\textrm{symbol error}] =  \frac{1}{M} \sum_{i=0}^{M-1} P[\textrm{symbol error} | H_i] $$
Since there are $2A$ between symbols, the threshold is going to be in between. 
## Symbol 0
When symbol 0 is sent, we have to exceed the threshold $-6A$ to get symbol error. $x$ is the value we measure, $-7A$ plus gaussian noise.
$$ P[\textrm{symbol error} | H_0] = P[x > -6A] = P\left[ \frac{x - (-7A)}{\sqrt{N_0/2}} > \frac{-6A-(-7A)}{\sqrt{N_0/2}} \right] $$
$x$ is not a standard normal random variable. We subtract the mean and divide by the SD. The term
$$ \frac{x - (-7A)}{\sqrt{N_0/2}} $$
is a standard normal variable we call $z$.
$$ P[z > \frac{A}{\sqrt{N_0/2}}] = Q\left(\frac{A}{\sqrt{N_0/2}} \right) $$
## Symbol 1
When symbol 1 is sent there are two ways to make an error. The symbol is centered at $-5A$, but if we go above $-4A$ or below $-6A$ we make a symbol error.
$$ P[\textrm{symbol error} | H_1] = P[x < -6A] + P[x > -4A] $$
We subtract the mean and divide by SD
$$ P\left[z < \frac{-6A -(-5A)}{\sqrt{N_0/2}}\right] + P\left[ z > \frac{-4A-(-5A)}{\sqrt{N_0/2}} \right] $$
The probability
$$ \Phi\left( \frac{-A}{\sqrt{N_0/2}} \right) + Q\left( \frac{A}{\sqrt{N_0/2}} \right) $$
Negating the argument of the Phi function gives the Q
$$ \Phi(-x) = Q(x) $$
So
$$ P[\textrm{symbol error} | H_1] = 2Q \left( \frac{A}{\sqrt{N_0/2}} \right) $$
## Total probability
$$  P[\textrm{symbol error}] =  \frac{1}{M} \sum_{i=0}^{M-1} P[\textrm{symbol error} | H_i]  $$
We have $M=8$ PAM. Two cases of
$$ Q\left(\frac{A}{\sqrt{N_0/2}} \right) $$
6 cases of
$$ 2Q \left( \frac{A}{\sqrt{N_0/2}} \right) $$
so
$$ P[\textrm{symbol error}] = \frac{1}{M} \left[ 2Q\left(\frac{A}{\sqrt{N_0/2}} \right) + 6\left(  2Q \left( \frac{A}{\sqrt{N_0/2}} \right) \right) \right] = \frac{14}{8}Q\left( \frac{A}{N_0/2}\right)$$
In general
$$ P[\textrm{symbol error}] = \frac{1}{M} \left[ 2Q\left(\frac{A}{\sqrt{N_0/2}} \right) + (M-2)  2Q \left( \frac{A}{\sqrt{N_0/2}}  \right) \right] $$
$$ =\frac{2(M-1)}{M} Q \left( \frac{A}{\sqrt{N_0/2}} \right)$$
## Expressed as energy
The energy per bit
$$ \epsilon_b  = \frac{1}{\log_2 M} \epsilon_s = \frac{1}{\log_2 M} \frac{(M^2 - 1)A^2}{3} $$
$$ A^2 = \frac{3 \log_2 M}{M^2 - 1} $$
We rewrite the probability
$$  \frac{2(M-1)}{M} Q \left( \frac{A}{\sqrt{N_0/2}} \right) = \frac{2(M-1)}{M} Q\left( \frac{2A^2}{N_0} \right) $$
We plug in the expression for $A^2$
$$ P[\textrm{symbol error}] = \frac{2(M-1)}{M} Q \left( \sqrt{ \frac{6 \log_2 M}{M^2 - 1} \frac{\epsilon_b}{N_0}} \right) $$
The term $\epsilon_b / N_0$ becomes unitless and determines the probability of error for any value of $M$. 
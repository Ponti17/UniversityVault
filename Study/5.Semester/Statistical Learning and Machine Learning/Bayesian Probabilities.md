# Prior and Posterior
Bayes' theorem is given by
$$ P(A|B) = \frac{P(B|A)P(A)}{P(B)} $$
where
![[Pasted image 20231214130726.png]]
The posterior conditional probability refers to probabilities obtained after the data has been taken into account, whereas the prior probability is obtained before our data has been taken into account.  

We now write Bayes' theorem as
$$ p(\mathbf{w}|\mathcal{D}) = \frac{p(\mathcal{D}|\mathbf{w})p(\mathbf{w})}{p(\mathcal{D})} $$
The quantity $p(\mathcal{D}|\mathbf{w})$ is evaluated for the observed data set $\mathcal{D}$ and can be viewed as a function of the parameter vector $\mathbf{w}$, in which case it is called the likelihood function. 

The denominator is a normalization constant, which ensures that the posterior distribution integrates to one. 
$$ p(\mathcal{D}) = \int p(\mathcal{D}|\mathbf{w})p(\mathbf{w}) d\mathbf{w} $$
Ina frequentist approach $\mathbf{w}$ is considered to be a fixed parameter whose value is determined by some form of estimator. From the Bayesian viewpoint there is only a single data set $\mathcal{D}$, and the uncertainty in the parameters is expressed through a probability distribution over $\mathbf{w}$. 

**Important**
One advantage of the Bayesian viewpoint is that the inclusion of prior knowl-
edge arises naturally. Suppose, for instance, that a fair-looking coin is tossed three
times and lands heads each time. A classical maximum likelihood estimate of the
probability of landing heads would give 1, implying that all future tosses will land
heads! By contrast, a Bayesian approach with any reasonable prior will lead to a
much less extreme conclusion.


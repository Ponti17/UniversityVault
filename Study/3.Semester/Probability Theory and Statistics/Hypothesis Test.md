# Hypothesis Test
---
A hypothesis is a premise or claim that we want to test.

The Null hypothesis is the "default" hypothesis i.e. the currently accepted value for a parameter. It is often denoted as $H_0$. 

The alternative hypothesis is a different claim to be tested. The alternative hypothesis is what we're testing for. It can be denoted as $H_a$. 

When testing there are only two possible outcomes:
- Reject null hypothesis.
- Fail to reject null hypothesis.

To decide if we reject the null hypothesis we need a test statistic calculated from sample data. When doing this we need a **level of confidence** described by a variable e.g. $c = 95\%$. The complement of this is the **level of signifiance** described by the variable $\alpha = 1 - c$. 

## One Tailed or Two Tailed
---
Whenever the alternative hypothesis simply does not equal the null hypothesis, we have a two tailed test. E.g. $$ H_0: \mu = 100g, \hspace{20pt} H_a = \mu \neq 100g $$ If for some other alternative hypothesis $H_a: \mu > 100g$ we would have an uppertailed test.

## One Sample T Test
---
For a one sample t-test we have a hypothesis that the mean of a population has some value e.g. $$ H_0: \mu = \mu_0, \hspace{20pt} H_a: \mu \neq \mu_0 $$
When performing a t-test the first step is the calculate mean, SD and finally the t-value. The t-value can be calculated by
$$ t_0 = \frac{\bar{x} - \mu_0}{SD/\sqrt{n}} $$
The critical value for a t-test can be calculated in R. For a two tailed test with $\alpha = 0.05$, $n = 20$
````R
qt(0.025, 19)
````
Depending on the alternative hypoothesis we will reject the null hypothesis if

![[ttest2.png]]

A t-test can by calculated from start to finish in R e.g.
````R
x = c(0.089, 0.077, 0.082, 0.092, 0.081, 0.083, 0.085, 0.080, 0.081, 0.091)

t.test(x, mu=0.08, alternative="greater")
````
The confidence interval can also be calculated in R 
````R
x = c(0.089, 0.077, 0.082, 0.092, 0.081, 0.083, 0.085, 0.080, 0.081, 0.091)

t.test(x, mu=0.08)
````
We note here that we must not use a one-sided t-test for the confidence interval.

## Two Sample T Test
---
For a two sample t-test our null hypothesis is that the population means are the same
$$ H_0: \mu_1 = \mu_2, \hspace{20pt} H_a: \mu_1 \neq \mu_2 $$
The t-value is given by (SD is squared)
$$ t = \frac{|\bar{x_1} - \bar{x_2}|}{\sqrt{ \frac{SD_1^2}{n_1} + \frac{SD_2^2}{n_2} }} $$
The critical value is calculated in R. For a 95% confidence interval and $n=n_1 + n_2 - 2 = 30$.
````R
qt(0.025, 30)
````

## Z Test
---
If we have at least $n \geq 30$ samples the z-values
$$ Z = \frac{\bar{x} - \mu_0}{SD/\sqrt{n}} $$
are normally distributed. Z-tests are performed when the standard deviation is known. It can performed in R by
````R
z.test(data, mu=100, sigma.x=15)
````

## Chi-squared Test
---
The Chi-squared test tells us if the variation in our data is due to chance or due to one of the variables.
$$ \chi_c^2 = \sum \frac{(O_i - E_i)^2}{E_i} $$

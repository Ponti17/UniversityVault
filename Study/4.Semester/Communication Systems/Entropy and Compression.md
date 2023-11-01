For a random variable $X$ with possible outcomes $x_i$, $i = 1, \ldots , n$. We have self-information
$$ I(x_i) = \log_2 \frac{1}{P(x_i)} $$
What does means is that the less likely and event is, the more information it carries. The entropy is the average of the self-information
$$ H(X) = \sum_{i=1}^n P(x_i)I(x_i) $$
## Example, English Language
In English, each letter has a certain probability of being in a word
$$ a = 8.167\%, \hspace{20pt} b = 1.492 \%, \hspace{20pt} \ldots $$
The entropy of the letters in the English language
$$ H(x) = 4.176 \,\textrm{bits/symbol} $$
So on average, we need 4.176 bits to represent each symbol. If each letter would be equally likely i.e. $1/26\%$ then 
$$ H(x) = 4.700 \,\textrm{bits/symbol} $$
If we know some characters appear more often than others, we can give it a shorter codeword.
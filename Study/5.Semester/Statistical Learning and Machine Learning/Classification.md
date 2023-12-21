# Nearest Class Centroid (NCC)
To compute class centroids, we take the average of all points in the class
$$ \mathbf{m}_{ci} = \frac{1}{N_{ci}} \sum_{i\in c_i} \mathbf{x_i} $$
To classify new points we then select the class with the lowest distance for $x_n$ to the centroid $m_k$
$$ y_n = \text{argmin} ||x_n - m_k|| $$
# Nearest Neighbor
Classification is done by assigning to the class with most nearest neighbors. For NN classification with one neighbor (1-NN)
$$ y_n = y_p $$
$$ p = \text{argmin} ||x_n - x_k || $$
# Bayes
In Bayesian classification we assign the class with highest conditional probability
$$ p(C_k|x_i) = \frac{p(x_i|C_k)p(C_k)}{p(x_i)} $$
$$ p(x_i|C_k) = \frac{||x_i - m_k||^{-2}}{\sum_{m=1}^2 ||x_i - m_m||^{-2}} $$
Having that $p(x_i)$ is fixed for a selected test points, the classification rule can be simplified to
$$ y_n = \text{argmax} p(x_i | C_k)p(C_k) $$
The class prior
$$ p(C_k) = \frac{N_k}{N} $$
where $N_k$ is the number of points belonging to the class $C_k$. Given this the predictive probability distribution is computed as
$$  y_n = \text{argmax} \frac{N_k||x_i - m_k||^{-2}}{N\sum_{m=1}^2 ||x_i - m_m||^{-2}}  $$
## Naive Bayes Example - StatQuest
Consider a total of 12 messages, 8 are normal messages and 4 are spam. The probability of different words occurring in the different types of messages
$$ p(\text{Dear}|N) = 0.47, \hspace{10pt} p(\text{Friend}|N) = 0.29 $$
$$ p(\text{Lunch}|N) = 0.18, \hspace{10pt} p(\text{Money}|N) = 0.06 $$
$$ p(\text{Dear}|S) = 0.29, \hspace{10pt} p(\text{Friend}|S) = 0.14 $$
$$ p(\text{Lunch}|S) = 0.00, \hspace{10pt} p(\text{Money}|S) = 0.57$$
Since the probabilities are discrete they are called likelihoods. Let us now say that we receive a message containing the words "Dear" and "Friend" and we want to classify it. We can make a simple guess
$$ p(N) = 8/12 = 0.67 $$
This is called a **Prior** probability. The **prior** can be any guess, but we based it on the classifications in the training set. We can multiply this with the probability of a normal message containing the words
$$ P(N) * p(\text{Dear}|N) * p(\text{Friend}|N) = 0.09 $$
we can think of this as the score that Dear Friend gets if it is a normal message. This is proportional to
$$ P(N) * p(\text{Dear}|N) * p(\text{Friend}|N) \propto p(N|\text{Dear Friend}) = 0.09 $$
The initial guess about the probability of the message being spam
$$ p(S) = 4/12 = 0.33 $$
Now we multiply the prior
$$  P(S) * p(\text{Dear}|S) * p(\text{Friend}|S) \propto p(S|\text{Dear Friend}) = 0.01  $$
Since the score we got for normal message is higher, the probability of the message being a normal message is highest. 

Let us now try to classify the message "Lunch Money Money Money Money".
$$ p(N) * p(\text{Lunch}|N) * p(\text{Money}|N)^4 = 0.000002 $$
$$ p(S) * p(\text{Lunch}|S) * p(\text{Money}|S)^4 = 0 $$
Since lunch occurs 0 times in spam, we get zero. 
# Whitening Transformation
Center the mean of the data on the origin, remove all covariances and the variance unitary. 
$$ \mathbf{x} \sim \mathcal{N}_D(\mu, \Sigma) \hspace{10pt} \rightarrow \hspace{10pt} \mathbf{y} \sim \mathcal{N}_D(0, \mathbf{I})  $$
The transformation
$$ \mathbf{y} = \Sigma^{-1/2} (\mathbf{x} - \mu) = WD^{-1/2}W^T(\mathbf{x - \mu}) $$
where
$$ W = [w_1, w_2, \ldots, w_D] $$
$$ D^{-0.5} = \begin{bmatrix} \lambda_1^{-0.5} & 0 & \ldots & 0 \\ 0 & \lambda_2^{-0.5} & \ldots & 0 \\ \vdots & \vdots & \end{bmatrix} $$
Since $W$ is orthogonal $W^{-1} = W^T$. 
$$ \Sigma = WDW^T = WD^{0.5}D^{0.5} W^T = (WD^{0.5}W^T)(WD^{0.5}W^T) = \Sigma^{0.5}\Sigma^{0.5} $$
$$ \Sigma^{-0.5} = (WD^{0.5}W^T)^{-1} = WD^{-0.5}W^T $$

We have
$$ A_1 = \Sigma = WDW^T $$
$$ A_2 = Y = D^{-0.5}W^T X $$
$$ A_3 = \Sigma Y =  $$

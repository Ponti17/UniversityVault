# Basic SVD-PCA Example
Consider the following data
![[Pasted image 20231218093009.png|400]]
We can plot this data along with their mean (blue)
![[Pasted image 20231218093309.png|400]]
we center the data by subtracting the means
![[Pasted image 20231218093520.png|400]]
We then fit a line through the origin and fit it as best as possible to the points
![[Pasted image 20231218093814.png|400]]
The linear line has $a \approx 0.25$ and is called PC1. We have gene1 on the x-axis and gene2 on the y-axis. This means the for 4 parts gene 1, we get 1 part gene 2. This is called a linear combination of genes 1 and 2. 

The vector along the fitted line has length $\sqrt{4^2 + 1^2} = 4.12$. We want to make this a unit vector. We do this by dividing the data with 4.12. The unit vector is the Eigenvector for PC1 and consists of $4/4.12 = 0.97$ gene 1, and $1/4.12 = 0.242$ gene 2. The proportions of each gene is called **loading scores**.

The average of the sum of squares distance for the best fit line is the Eigenvalue for PC1. The square root of the sum of squares distances is the singular value for PC1.

The line PC2 is the line that is perpendicular to PC1. I.e. it is described by the unit vector $(-0.242, 0.97)$. (Also the negative reciprocal of $a$)
![[Pasted image 20231218095351.png|400]]
We now rotate everything around the origin so PC1 lies on the x-axis
![[Pasted image 20231218100059.png|400]]
We are now done. We see that PC1 accounts for much more of the variation than PC2. 




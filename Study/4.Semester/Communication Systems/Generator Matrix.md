To generate codeword c from information i
$$ [c] = [i] [G] $$
The generator matrix of an $(n,k)$ linear code where $k$ is rows and $n$ is columns. Generator matrix for (7,4) code
$$ [G] = [I :P] $$
where I is identity matrix, and P is parity matrix.
$$ G = 
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 1 \\
1 & 1 & 1 \\
1 & 1 & 0 \\
0 & 1 & 1 \\
\end{bmatrix}
$$
The matrix should not be multiplied. They are simply joined. For a message 
$$ [i] =
\begin{bmatrix}
1 & 1 &1 & 0 \\
\end{bmatrix}
$$
We then multiply information matrix with generator matrix
$$
[c] = 
\begin{bmatrix}
1 & 1 &1 & 0 \\
\end{bmatrix}
*
\begin{bmatrix}
1 & 0 & 0 & 0 & 1 & 0 &1 \\
0 & 1 & 0 & 0 & 1 & 1 & 1\\
0 & 0 & 1 & 0 & 1 & 1 & 0 \\
0 & 0 & 0 & 1 & 0 & 1 & 1\\
\end{bmatrix}
=
\begin{bmatrix}
1 & 1 & 1 & 0 & 1 & 0 & 0 \\
\end{bmatrix}
$$


## Example
For a $[7,4]$ code with 
$$ G = 
\begin{bmatrix}
1 & 0 & 0 & 0 & 1 & 1 & 0 \\
0 & 1 & 0 & 0 & 0 & 1 & 1 \\
0 & 0 & 1 & 0 & 1 & 1 & 1 \\
0 & 0 &0 & 1 & 1 & 0 & 1 \\
\end{bmatrix}
$$
We first count the rows. We see that G has 4 rows. We then find all binary row vectors with length 4 i.e. any combination of 1 and 0. 
$$ 4^2 = 16 $$
![[Pasted image 20230621103846.png]]
We then multiply row vectors and G


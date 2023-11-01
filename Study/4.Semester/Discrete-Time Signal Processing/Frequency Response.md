If a system is stable then
$$ H(z) \Rightarrow \textrm{ROC includes } |z| = 1 $$
i.e. the region of convergence includes the unit circle. Therefore we can substitute
$$ H(e^{j\omega}) = H(z) \Big|_{z=e^{j\omega}} = \frac{\sum\limits_{k=0}^{M}b_k e^{-j\omega k}}{\sum\limits_{k=0}^{n}a_k e^{-j\omega k}}$$
this can be rewritten to pole/zero form
$$ H(e^{j\omega}) = \frac{b_0}{a_0} \frac{\prod_{k=0}^{M}(1 - c_k e^{-j\omega})}{\prod_{k=0}^{N}(1 - d_k e^{-j\omega})} $$
The magnitude is then
$$ |H(e^{j\omega})| = \frac{|b_0|}{|a_0|} \frac{\prod_{k=0}^{M}|e^{j\omega} - c_k|}{\prod_{k=0}^{N}|e^{j\omega} - d_k|} $$
We see that the magnitude response is dependent on terms like $|e^{j\omega} - a|$. The term $e^{j\omega}-a$ is a vector connecting $e^{j\omega}$ to a point $a$ in the complex plane. $L = |e^{j\omega} -a|$ is the length of this vector.
![[magResponse.png]]
We can therefore consider the magnitude response as the product of the distance from $e^{j\omega}$ to zeros divided by the product of the distance from $e^{j\omega}$ to poles.

When $e^{j\omega}$ is close to a zero, $|H(e^{j\omega})|$ is small. 

When $e^{j\omega}$ is close to a pole, $|H(e^{j\omega})|$ is large.

## Example
If we consider the system function
$$ H(z) = \frac{1}{1 - \frac{3}{4}z^{-1}} $$
then we see that we have a zero at $z = 0$, and a pole at $z = 3/4$. At a frequency $\omega_1$ 
![[omega1.png]]
the distance to the zero $L_z \approx 1$, the distance to the pole $L_p \approx 1/4$. The gain is therefore
$$ |H(e^{j\omega_1})| \approx \frac{1}{1/4} = 4$$
We can do this all the way around the unit circle to calculate the magnitude response
![[magResponse 1.png]]

## Example 2
Consider a system with the zero-pole plot
![[zp1.png]]
A zero is located at $\omega = 0$, so the gain will start off small. At  $\omega = \pi/4$ the pole will increase the magnitude. The frequency response is shown below
![[freq1.png]]
```
z = [1, -1]'
p = [0.95*exp(j*pi/4), 0.95*exp(-j*pi/4)]'
k = 1
[b,a] = zp2tf(z,p,k)
zplane(z,p)
[h,w] = freqz(b,a)
plot(abs(w), h)
```

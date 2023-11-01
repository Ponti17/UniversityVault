# Fourier Series Expansion
---
Fourier series expansion is used for periodic signals to expand them in terms of their harmonics which are sinusoidal and orthogonal to one another.

For **periodic signals** we have the continuous-time Fourier series and the discrete-time Fourier series.

For **non-periodic** signals we have the continuous-time Fourier transform and the discrete-time Fourier transform.

In contrast to Z/Laplace transform which is used for design (obtain transfer function), Fourier series/transform is used for analysis.

The output of the Fourier expansion will usually be some combination of
$$ \textrm{Fourier Series} = DC + \sin + \cos$$
There a three forms of Fourier series expansion

1. Trigonometric FS
2. Complex Exponential FS
3. Polar/Harmonic FS

## Existence of Fourier Series
---
Even though a signal may be periodic it does not mean it has a fourier series expansion. The conditions for Fourier expansion are known as the Dirichlet conditions.

**Condition 1.**
The signal should have finite number of maxima and minima over the range of time period. Consider the signals shown below. The upper has a clear finite amount of maxima and minima in a time period.
![[dirichlet1.png]]

**Condition 2.**
The signal should have finite number of discontinuities over the range of time period. Consider the signals shown below. The upper has a clear finite amount of discontinuities in a time period.
![[dirichlet2.png]]

**Condition 3.**
Signal should be absolutely integrable over the range of time period. Consider the signals shown below. The upper signal is absolutely integrable.
![[dirichlet3.png]]
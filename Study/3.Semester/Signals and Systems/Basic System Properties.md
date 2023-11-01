# Basic System Properties
---
Systems have 6 properties

- Static and Dynamic Systems
- Causal and Non-Causal Systems
- Time-Invariant and Time-Variant Systems
- Linear and Non-Linear Systems
- Invertible and Non-Invertible Systems
- Stable and Unstable Systems

## Dependence on Past, Present, Future
---
We consider the system
$$ x(t) \rightarrow y(t) $$
We have three cases
$$ y(t) = x(t) $$
$$ y(t) = x(t - 1) $$
$$ y(t) = x(t + 1) $$
If we set $t = 0$, we see that 
$$ y(0) = x(0) $$
$$ y(0) = x(-1) $$
$$ y(0) = x(1) $$
Which means that the first case depends on the present. The second case depends on the past and the third case depends on the future. 

## Static and Dynamic Systems
---
**Static System:** Output depends only on present values of input.
$$ y(t) = f(x(t))$$
**Dynamic System:** Output depends on past or future values of input at any instant of time. (Can also depend on present at some points in time). To determine if a system is static or dynamic we do not consider coefficients e..g
$$ y(t) = e^{-(t+1)} x(t)$$
is a static system even though $t$ appears in the coefficient.

## Causal and Non-Causal Systems
---
**Causal System:** Output of system is independent of future values of input. e.g.
$$ y(t) = x(t) + x(t-1) $$
ALL real life systems are causal.

**Non-Causal System:** Output of system depends on future values of input at any instant of time. e.g.
$$ y(t) = x(t + 2) $$
or
$$ y(t) = x(t) + x(t -1) + x(t + 1) $$

## Time-Invariant and Time-Variant Systems
---
A time invariant system is a system in which any delay provided in the input must be reflected in the output. Consider the diagram
![[time_inva.png]]
There are two possibilities
$$ y'(t) \begin{cases}
= y(t-t_{0}), \hspace{10pt} \textrm{Time-Invariant} \\
\neq y(t - t_{0}), \hspace{10pt} \textrm{Time-Variant} \\
\end{cases}
$$
Whenever a system performs time shifting it is time-variant. If it performs amplitude shifting it is time-invariant.
### Example 1
$$ y(t) = x(2t) $$
So we have the system
$$ x(t) \rightarrow system \rightarrow x(t) = y(t) $$
First we prodivde the delay to the output
$$ y(t) \rightarrow t_{o}\rightarrow y(t-t_{0}) =x[2(t-t_{0})]= x(2t-2t_0) $$
Now we provide the delay to the input
$$ x(t) \rightarrow t_{0}\rightarrow x(t-t_{0)}$$
Now we give this as the input to the system
$$ x(t-t_{0}) \rightarrow t_{0} \rightarrow x(2t-t_{0}) $$
### Example 2
$$ y(t) = 2 + x(t) $$
So we have the system
$$ x(t) \rightarrow system \rightarrow 2 + x(t) = y(t) $$
We provide delay to the output
$$ y(t) \rightarrow t_{0}\rightarrow y(t - t_{0}) = 2 + x(t - t_0)$$
We provide the delay to the input
$$ x(t - t_{0}) \rightarrow 2 + x(t - t_{0}) $$

## Linear and Non-Linear Systems
---
**Linear Systems:** A system which follows the principle of superposition.

**Non-Linear Systems:** A system which does not follow the principle of superposition.

The principle of superposition has two laws:

**1. Law of Additivity**
Consider the two cases
$$ x_1(t) \rightarrow y_1(t)$$
$$ x_2(t) \rightarrow y_2(t) $$
Summing the two inputs
$$ x_1(t) + x_2(t) \rightarrow y'(t) $$
If
$$ y'(t) = y_1(t) + y_2(t) $$
the system is following the law of additivity.

**2. Law of Homogenity**
Consider the case
$$ x(t) \rightarrow y(t) $$
We multiply the input with a constant
$$ kx(t) \rightarrow y'(t) $$
If
$$ y'(t) = ky(t) $$
The system is following the law of homogenity.

**Example**
Consider the system
$$ x(t) \rightarrow y(t) = x(\sin t)$$
We see that
$$ y_1(t) = x_1(\sin t), \hspace{20pt} y_2(t) = x_2(\sin t)$$
So
$$ y_1(t) + y_2(t) = x_1(\sin t) + x_2(\sin t)$$
If we sum the inputs (we see that the system replaces t with $\sin t$)
$$ x_1(t) + x_2(t) \rightarrow x_1(\sin t) + x_2(\sin t)$$
So the law of additivity holds. If we multiply output with a constant
$$ ky(t) = kx(\sin t)$$
If we multiply the input with a constant
$$ kx(t) \rightarrow kx(\sin t)$$
We see that the system follows the law of homogenity. So the system is linear.

## Stable and Unstable Systems
---
Stable systems are systems which follows BIBO (Bounded Input Bounded Output). 

**BIBO:** For a stable system output should be bounded for bounded input at each and every instant of time.

Bounded means confining something to a limited range. For signals we are limiting the amplitude. From $-\infty$ to $\infty$ the amplitude should not reach $\infty$ i.e. it is finite. An unstable is a system which gives an unbounded output for a bounded input.

**Bounded Signals**
DC, $\sin(t)$, $\cos(t)$, $u(t)$

**Example** 1
We have the system
$$ x(t) \rightarrow y(t) = tx(t)$$
If we give the system the bounded input $u(t)$
$$ u(t) \rightarrow tu(t) $$
$tu(t)$ is the unit ramp function. As time goes to infinity the output goes to infinity. So the system is unstable. 

**Example 2**
We have the system
$$ x(t) \rightarrow y(t) = x(t) + 2$$
If we give the system the bounded DC input $4$
$$ 4 \rightarrow 4 + 2$$
As time goes to infinity the output is bounded. The system is stable.

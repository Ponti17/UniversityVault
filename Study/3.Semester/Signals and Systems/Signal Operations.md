## Addition of Continuous Time Signals
---
If we have two signals
$$ x_1(t), \hspace{20pt} x_2(t) $$
The sum is 
$$ x_3(t) = x_1(t) + x_2(t) $$

## Multiplication of Continuous Time Signals
---
If we have two signals 
$$ x_1(t), \hspace{20pt} x_2(t) $$
The product is
$$ x_3(t) = x_1(t) x_2(t) $$

## Time Scaling of Continuous Time Signals
---
Time scaling is the compression or expansion of a signal in time.  When time scaling a signal $x(t)$ to get the result $y(t)$, we multiply $t$ with a non-zero value $\alpha$. 
$$ x(t) \rightarrow y(t) = x(\alpha t), \hspace{10pt} \alpha = 0 $$
**Case 1, time compression**:
$$ \alpha \in (-\infty, -1) \cup (1, \infty) $$
i.e. $\alpha \neq 0.1, 0.2$ etc. This is called time compression.

**Case 2, time expansion**:
$$ \alpha \in (-1, 0) \cup (0, 1) $$
This is called time expansion.

## Amplitude Scaling of Continuous Time Signals
---
When amplitude scaling a signal $x(t)$ to get the result $y(t)$, we multiply with a value $\beta$.
$$ x(t) \rightarrow y(t) = \beta x(t) $$

## Time Shifting of Continuous Time Signals
---
When time shifting a signal $x(t)$ to get the result $y(t)$ we add a constant $k$ to the time.
$$ x(t) \rightarrow y(t) = x(t + k) $$
**Case 1**:
$$ k > 0 $$
The signal moves to the left.

**Case 2**:
$$ k < 0 $$
The signal moves to the right.

## Amplitude Shifting of Continuous Time Signals
---
When  amplitude shifting a signal $x(t)$ to get the reuslt $y(t)$, we add a constant $k$.
$$ x(t) \rightarrow y(t) = x(t) + k $$
The original waveform remains the same, but moves up/down the y-axis.

## Reversal of Continuous Time Signals
---
**Case 1, Time Reversal**:
Special case of time scaling with $\alpha = -1$. 
$$ x(t) \rightarrow y(t) = x(-t) $$
**Case 2, Amplitude Reversal**:
Special case of amplitude scaling with $\beta = -1$. 
$$x(t) \rightarrow y(t) = -x(t) $$

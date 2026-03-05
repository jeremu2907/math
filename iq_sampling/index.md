[$\leftarrow$ Back](../index.html)
### IQ Sampling Circuit Analysis

#### Introduction

Obviously IQ sampling can be derived using complex exponential without the need of hardware implementation. This article, however, will concern itself with how each circuit component applies a mathematical operation on the analog signal to produce the IQ values.

#### Primer

The received signal from an antenna, $s(t)$, is represented as 
$$
s(t) = A \cos{(\omega t + \phi)}
$$
Which can be written in exponential form using [Euler's Formula](../eulers_identity/index.html)
$$
s(t) = \frac{A}{2}(e^{j (\omega t + \phi)} + e^{-j (\omega t + \phi)})
$$
Note that $A$ and $\phi$ are actually functions encoding the message depending on the type of modulation. For the sake of notation simplicity $A = A(t)$ and $\phi = \phi(t)$.

#### The Circuit

![alt text](image.png)

Here, the RF input signal is $s(t)$. $s(t)$, the local oscillator signal $LO(t)$ and its shifted signal $LO_Q(t)$ are fed to mixers going to the $I$ and $Q$ branch, respectively.

#### In-Phase Component, $I$

The local oscillator signal $LO(t)$ is
$$
LO(t) = \cos{(\omega t)} = \frac{1}{2}(e^{j \omega t} + e^{-j \omega t})
$$

When $s(t)$ and $LO$ are mixed using an ideal mixer, the result is

$$
\begin{aligned}
s(t) \times LO(t) &= A \cos{(\omega t + \phi)} \times \cos{(\omega t)}
\\
&= \frac{A}{2}(e^{j (\omega t + \phi)} + e^{-j (\omega t + \phi)}) \times \frac{1}{2}(e^{j \omega t} + e^{-j \omega t}) \\
\\
&= \frac{A}{4}(e^{j (\omega t + \phi)} + e^{-j (\omega t + \phi)}) \times (e^{j \omega t} + e^{-j \omega t}) \\
\\
&= \frac{A}{4}(e^{j (2 \omega t + \phi)} + e^{j \phi} + e^{-j \phi} + e^{-j (2 \omega t + \phi)}) \\
\\
&= \frac{A}{4}(e^{j (2 \omega t + \phi)} + e^{-j (2 \omega t + \phi)} + e^{j \phi} + e^{-j \phi}) \\
\\
&= \frac{A}{2} \left( \frac{e^{j (2 \omega t + \phi)} + e^{-j (2 \omega t + \phi)}}{2} + \frac{e^{j \phi} + e^{-j \phi}}{2} \right) \\
\\
&= \frac{A}{2} (\cos{(2 \omega t + \phi)} + \cos{(\phi)})
\end{aligned}
$$

$I$, the signal $s(t) \times LO(t)$ after low pass filter is
$$
\begin{aligned}
I &= \text{LPF}\{s(t) \times LO(t)\} \\
\\
&= \text{LPF}\left\{\frac{A}{2} (\cos{(2 \omega t + \phi)} + \cos{(\phi)})\right\} \\
\\
&= \frac{A}{2} \times \text{LPF}\{\cos{(2 \omega t + \phi)} + \cos{(\phi)}\} \\
\\
&= \frac{1}{2} A \cos{(\phi)}
\end{aligned}
$$

#### Quadrature-Phase Component, $Q$

The $90\degree$ shifted local oscillator signal $LO_Q(t)$ is
$$
LO_Q(t) = \cos{(\omega t + 90 \degree)} = -\sin{(\omega t)} = -\frac{1}{2j}(e^{j \omega t} - e^{-j \omega t})
$$

When $s(t)$ and $LO_Q(t)$ are mixed using an ideal mixer, the result is

$$
\begin{aligned}
s(t) \times LO_Q(t) &= A \cos{(\omega t + \phi)} \times -\sin{(\omega t)}
\\
&= \frac{A}{2}(e^{j (\omega t + \phi)} + e^{-j (\omega t + \phi)}) \times -\frac{1}{2j}(e^{j \omega t} - e^{-j \omega t}) \\
\\
&= -\frac{A}{4j}(e^{j (\omega t + \phi)} + e^{-j (\omega t + \phi)}) \times (e^{j \omega t} - e^{-j \omega t}) \\
\\
&= -\frac{A}{4j}(e^{j (2 \omega t + \phi)} - e^{j \phi} + e^{-j \phi} - e^{-j (2 \omega t + \phi)}) \\
\\
&= -\frac{A}{4j}(e^{j (2 \omega t + \phi)} - e^{-j (2 \omega t + \phi)} - e^{j \phi} + e^{-j \phi}) \\
\\
&= -\frac{A}{4j}(e^{j (2 \omega t + \phi)} - e^{-j (2 \omega t + \phi)} - (e^{j \phi} - e^{-j \phi})) \\
\\
&= -\frac{A}{2} \left( \frac{e^{j (2 \omega t + \phi)} - e^{-j (2 \omega t + \phi)}}{2j} - \frac{e^{j \phi} - e^{-j \phi}}{2j} \right) \\
\\
&= -\frac{A}{2} (\sin{(2 \omega t + \phi)} - \sin{(\phi)})
\end{aligned}
$$

$Q$, the signal $s(t) \times LO_Q(t)$ after low pass filter is
$$
\begin{aligned}
Q &= \text{LPF}\{s(t) \times LO_Q(t)\} \\
&= \text{LPF}\left\{-\frac{A}{2} (\sin{(2 \omega t + \phi)} - \sin{(\phi)})\right\} \\
&= -\frac{A}{2} \times \text{LPF}\{\sin{(2 \omega t + \phi)} - \sin{(\phi)}\} \\
&= \frac{1}{2} A \sin{(\phi)}
\end{aligned}
$$

Thus

$$I = \frac{1}{2} A \cos{(\phi)}$$

$$Q = \frac{1}{2} A \sin{(\phi)}$$


#### Properties of $(I, Q)$

For all $i$ from $1$ to $n$:

$$A_i = 2\sqrt{I_i^2 + Q_i^2}$$

$$\phi_i = \text{atan2}{(Q_i, I_i)}$$

$A_i$ is the instantaneous envelope amplitude of the signal.
$\phi_i$ is the instantaneous phase of the signal.

#### Reconstructing Discrete $s(t)$

For all $i$ from $1$ to $n$:

$$
\begin{aligned}
s_i &= 2(I_i \cos{( \omega t)} - Q_i \sin{( \omega t)}) \\
&= A_i\cos{(\phi_i)}\cos{( \omega t)} - A_i\sin{(\phi_i)}\sin{( \omega t)} \\
\end{aligned}
$$

Using the identity $\cos(\alpha + \beta) = \cos\alpha\cos\beta - \sin\alpha\sin\beta$ , the expression can be rewritten

$$
\begin{aligned}
& A_i\cos{(\phi_i)}\cos{( \omega t)} - A_i\sin{(\phi_i)}\sin{( \omega t)} \\
&= A_i \cos(\omega t + \phi_i)
\end{aligned}
$$

This is the discrete signal $s_d(t)$ of $s(t)$.
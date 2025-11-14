[$\leftarrow$ Back](../index.html)
### Nth Order Homogeneous ODE With Constant Coefficient Solution

#### 1. Let there be an ODE in the form:

$$
y^{(n)} + a_1y^{(n - 1)} + a_2y^{(n - 2)} + ... + a_ny = 0
$$

$a_i \in \mathbb{R}$
$y^{(k)}$ is the $k^{th}$ derivative of $y$
$y^{(0)} = y$

#### 2. Let $\mu$ be a function, assume a special property that $y^{(n)}$ has: {#section2}

$$
\begin{aligned}
y^{(n)} &= \mu \ y^{(n-1)} \\
&= \mu \ \mu \ y^{(n-2)} \\
&= \mu^{2} \ y^{(n-2)} \\
& \ ... \\
&= \mu^{n}y
\end{aligned}
$$

#### 3. It follows that the ODE can be rewritten: {#section3}

$$
\begin{aligned}
y^{(n)} + a_1y^{(n - 1)} + a_2y^{(n - 2)} + ... + a_ny = 0 \\
\mu^{n}y + a_1\mu^{n - 1}y + a_2\mu^{n - 2}y + ... + a_ny = 0 \\
\mu^{n} + a_1\mu^{n - 1} + a_2\mu^{n - 2} + ... + a_n = 0 \\
\end{aligned}
$$

This is a polynomial equation of $\mu$. From here, solve for $\mu$ as if solving an nth-degree polynomial. By the [fundamental theorem of algebra](https://en.wikipedia.org/wiki/Fundamental_theorem_of_algebra), a nth-degree polynomial of $\mu$ has exactly n complex roots. Furthermore, if a root of a single variable polynomial with real coefficients is complex, then its complex conjugate is also a root. Thus, the solutions for $\mu$ are n complex numbers of the form:
$$\mu = a \pm bi, \qquad a,b \in \mathbb{R}$$

#### 4. Solving for y

Since the ODE is in terms of $y$ from section [3](#section3), assuming the n solutions for $\mu$, and implied from section [2](#section2), $\mu$ is a coefficient of the separable differential equation:

$$
\begin{aligned}
y^{(1)} &= \mu \ y^{(0)} \\
y' &= \mu \ y \\
\frac{dy}{dx} &= \mu \ y \\
\frac{dy}{y} &= \mu \ dx \\
\ln{y} &= \mu \ x + C \\
y &= Ke^{\mu \ x} \\
\end{aligned}
$$

##### 4.1. If $\mu$ has an imaginary component
When $\mu = a \pm bi, \qquad a,b \neq 0$
$$
\begin{aligned}
y &= Ke^{(a \pm bi)x} \\
y &= Ke^{ax \pm ibx} \\
y &= Ke^{ax}e^{\pm ibx} \\
\end{aligned}
$$
Since $e^{ix} = \cos(x) + i\sin(x) \ \text{and} \sin(-x) = -\sin(x)$:
$$
\begin{aligned}
y_1 &= K_1e^{ax}\cos(bx) + iK_1e^{ax}\sin(bx) \\
y_2 &= K_2e^{ax}\cos(bx) - iK_2e^{ax}\sin(bx) \\
\end{aligned}
$$

The coefficients can be absorbed, generalizing the solution for $\mu$ to be:

$$
\begin{aligned}
y &= C_1e^{ax}\cos(bx) + C_2e^{ax}\sin(bx) \\
\end{aligned}
$$

Note that this is the solution for a single $\mu$. Given n $\mu$, given an n-degree polynomial, the general solution for all $\mu$ is:

$$
\begin{aligned}
y &= \sum_{k = 1}^{n}{C_{k1}e^{a_{k}x}\cos(b_{k}x) + C_{k2}e^{a_{k}x}\sin(b_{k}x)}
\end{aligned}
$$

##### 4.2. If $\mu$ is a real number (no imaginary component)
When $\mu = a \pm bi, \qquad b =0$
$$
\begin{aligned}
y &= Ce^{ax} \\
\end{aligned}
$$

Note that this is the solution for a single $\mu$. Given n $\mu$, given an n-degree polynomial, the general solution for all $\mu$ is:

$$
\begin{aligned}
y &= \sum_{k = 1}^{n}{C_{k}e^{a_{k}x}}
\end{aligned}
$$
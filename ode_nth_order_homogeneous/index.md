[$\leftarrow$ Back](../index.html)
### Nth Order Homogeneous ODE With Constant Coefficients Solution

This article will show that the general solution for a homogeneous ODE with constant coefficients of the form

$$
y^{(n)} + a_1y^{(n - 1)} + a_2y^{(n - 2)} + ... + a_ny = 0
$$

is

$$
y = \sum_{k = 1}^{n}{C_{k1}e^{a_{k}x}\cos(b_{k}x) + C_{k2}e^{a_{k}x}\sin(b_{k}x)}
$$

**Lemma 1.**
Let $\mu$ be a complex number. Suppose $y^{(n)}$ satisfies the recurrence

$$
y^{(n)} = \mu \ y^{(n-1)} \quad \text{for all } n \geq 1
$$

Then

$$
y^{(n)} = \mu^n y
$$

Proof using induction on $n$.

Base Case:

$$
\begin{aligned}
y^{(0)} &= \mu^{0}y \\
y^{(0)} &= y
\end{aligned}
$$

Induction Hypothesis:

For some $k \geq 0$
$$
y^{(k)} = \mu^k y
$$

Induction Step:

$$
\begin{aligned}
y^{(k+1)} &= \mu y^{(k)} \\
y^{(k+1)} &= \mu \mu^k y \\
y^{(k+1)} &= \mu^{(k + 1)} y
\end{aligned}
$$
Hence, the statement is true for all $n \geq 0$.

**The Characteristic Equation**
The ODE can be rewritten using **Lemma 1** as

$$
y^{(n)} + a_1y^{(n - 1)} + a_2y^{(n - 2)} + ... + a_ny = 0 \\
\Downarrow \\
\mu^{n}y + a_1\mu^{n - 1}y + a_2\mu^{n - 2}y + ... + a_ny = 0
$$

Assuming non-trivial solutions $y \neq 0$, divide both sides by $y$ yields

$$
\begin{aligned}
\mu^{n} + a_1\mu^{n - 1} + a_2\mu^{n - 2} + ... + a_n = 0 \\
\end{aligned}
$$

This is a polynomial equation of $\mu$. From here, solve for $\mu$ as if solving an nth-degree polynomial. By the [fundamental theorem of algebra](https://en.wikipedia.org/wiki/Fundamental_theorem_of_algebra), a nth-degree polynomial of $\mu$ has exactly n complex roots. Furthermore, if a root of a single variable polynomial with real coefficients is complex, then its complex conjugate is also a root. Thus, the solutions for $\mu$ are n complex numbers of the form

$$\mu = a \pm bi, \qquad a,b \in \mathbb{R}$$

Each $\mu$ is a coefficient of the separable differential equation:

$$
\begin{aligned}
\frac{dy}{dx} &= \mu \ y \\
\frac{1}{y} dy &= \mu \ dx \\
\ln{y} &= \mu \ x + C \\
y &= Ke^{\mu \ x} \\
y &= Ke^{(a \pm bi)x} \\
y &= Ke^{ax \pm ibx} \\
y &= Ke^{ax}e^{\pm ibx} \\
\end{aligned}
$$

By [Euler's Formula](../eulers_identity/index.html), $e^{ix} = \cos(x) + i\sin(x)$ and $\sin(-x) = -\sin(x)$

$$
\begin{aligned}
y_1 &= K_1e^{ax}\cos(bx) + iK_1e^{ax}\sin(bx) \\
y_2 &= K_2e^{ax}\cos(bx) - iK_2e^{ax}\sin(bx) \\
\end{aligned}
$$

The coefficients are absorbed, generalizing the solution for $\mu$ to be

$$
\begin{aligned}
y &= C_1e^{ax}\cos(bx) + C_2e^{ax}\sin(bx) \\
\end{aligned}
$$

For a n-degree polynomial, the general solution for all $\mu$ is a linear combination

$$
\begin{aligned}
y &= \sum_{k = 1}^{n}{C_{k1}e^{a_{k}x}\cos(b_{k}x) + C_{k2}e^{a_{k}x}\sin(b_{k}x)}
\end{aligned}
$$

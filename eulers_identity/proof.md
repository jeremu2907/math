### Euler's Identity

$z$ is a point on the complex plane, where by definition:
$$
z = a + bi, \qquad a,b \in \mathbb{R}$$

Consider the complex unit circle $D = \{\, a+bi \in \mathbb{C} \mid a^2 + b^2 = 1\}$

Let $z(\theta):\mathbb{R}\rightarrow\mathbb{C}$ be a function on $D$, which shows that the following is true:
$$
a = \cos{\theta},\; b = \sin{\theta}
$$

Thus:
$$
z(\theta) = \cos{\theta}  + i\sin{\theta} \tag{1} \\
$$

When $\theta = 0$:
$$
\begin{aligned}
z(0) &= \cos{0} + i\sin{0} \\
z(0) &= 1 \tag{2}
\end{aligned}
$$

$z'(\theta)$ is the derivative of $z(\theta) $:
$$
\begin{aligned}
z'(\theta) &= -\sin(\theta) + i \cos(\theta) \\
-z'(\theta) &= \sin(\theta) - i \cos(\theta) \\
-i\;z'(\theta) &= i\sin(\theta) + \cos(\theta) \\
-i\;z'(\theta) &=  \cos(\theta) + i\sin(\theta) \\
-i\;z'(\theta) &= z(\theta) \qquad \text{from (1)} \\
z'(\theta) &= -\frac{1}{i} z(\theta) \\
z'(\theta) &= \frac{i^2}{i} z(\theta) \\
z'(\theta) &= i\;z(\theta) \\
\frac{1}{z(\theta)} \frac{\mathrm{d}z(\theta)}{\mathrm{d}\theta}  &= i \\
\frac{1}{z(\theta)} \mathrm{d}z(\theta)  &= i\;\mathrm{d}\theta \\
\int \frac{1}{z(\theta)} \mathrm{d}z(\theta)  &= \int i\;\mathrm{d}\theta \\
\ln(z(\theta)) &= i\theta + C \\
z(\theta) &= e^{i\theta + C} \tag{3}
\end{aligned}
$$

Solving for C:
$$
\begin{aligned}
z(0) &= e^{i0 + C} = e^C\\
z(0) &= 1 \qquad \text{from (2)} \\
e^{C}\ &= 1 \\
C &= 0
\end{aligned}
$$

Apply $C = 0$ to $(3)$:
$$
\begin{aligned}
z(\theta) &= e^{i\theta} \\
\end{aligned}
$$

However from $(1)$, $z(\theta) = \cos{\theta}  + i\sin{\theta}$,
thus:

$$
\begin{aligned}
\cos{\theta}  + i\sin{\theta} &= e^{i\theta} \\
e^{i\theta} &= \cos{\theta}  + i\sin{\theta} \tag{4}\\
\end{aligned}
$$

When $\theta = \pi$:
$$
\begin{aligned}
e^{i\pi} &= \cos{\pi}  + i\sin{\pi} \\
e^{i\pi} &= -1 \\
e^{i\pi} + 1 &= 0
\end{aligned}
$$

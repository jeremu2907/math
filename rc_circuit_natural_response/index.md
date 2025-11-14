[$\leftarrow$ Back](../index.html)
### LC Circuit Natural Response
![alt text](image-1.png)

Consider the circuit above. An inductor L is in series with a capacitor C. At $t = 0$ there is an initial current $I_0$ and there is no voltage different between the two plates of the capacitor. Let $i_{L}(t)$, $v_{C}(t)$ be L's current function of time and C's voltage function of time, respectively. At t = 0:

$i_{L}(0) = i_{C}(0) = I_{0}$
$v_{C}(0) = v_{0} = 0V$

#### 1. Passive Component Properties
The following is are useful characteristic functions we are interested in:

##### 1.1 Inductor
$$
\begin{aligned}
v &= L\frac{di}{dt}\\
L di &= v dt \\
di &= \frac{1}{L} v dt \\
i_{L} &= \frac{1}{L}\int{v dt} + i_0
\end{aligned}
$$

Using passive sign convention, $v$ in this equation will be $-v$. So:

$$
\begin{aligned}
i_{L} &= -\frac{1}{L}\int{v dt} + i_0
\end{aligned}
$$

##### 1.2 Capacitor
$$
\begin{aligned}
v &= \frac{q}{C} \\
Cv &= q \\
C\frac{d}{dt}v &= \frac{d}{dt}q
\end{aligned}
$$
$\frac{d}{dt}q$ is current, i, thus:
$$
\begin{aligned}
C\frac{d}{dt}v &= \frac{d}{dt}q \\
\\
i_{C} &= C\frac{d}{dt}v
\end{aligned}
$$

Using passive sign convention, $v$ in this equation will be $+v$.

#### 2. Describing the Circuit As a Differential Equation

Since the two components, L and C, are connected in series, the current are equal in magnitude. Thus:

$$i_{L} = i_{C}$$

Replacing $i$ with expressions containing $v$ obtained from [1.1](#11-inductor) and [1.2](#12-capacitor)
$$
\begin{aligned}
i_{L} &= i_{C} \\
-\frac{1}{L}\int{v dt} + i_0 &= C\frac{d}{dt}v \\
\\
\frac{d}{dt}\left[-\frac{1}{L}\int{v dt} + i_0\right] &= \frac{d}{dt}\left[C\frac{d}{dt}v\right] \\
\\
-\frac{1}{L}v &= Cv'' \\
\\
Cv'' + \frac{1}{L}v &= 0 \\
\\
v'' + \frac{1}{LC}v &= 0 \\
\end{aligned}
$$

#### 3. Solving for $v(t)$
Solving this yields:

$$
\begin{aligned}
v(t) &= \frac{I_{0}}{C\omega}\sin{(wt)} \\
\text{where} \\
\omega &= \frac{1}{\sqrt{LC}}
\end{aligned}
$$

[$\rightarrow$ See this article on solving 2nd Order Linear Homogenous ODE](../ode_nth_order_homogeneous/index.html)

From [1.2](#12-capacitor)
$$
\begin{aligned}
i_{C} &= C\frac{d}{dt}v \\
\\
i_{C} &= C\frac{d}{dt}\left[\frac{I_{0}}{C\omega}\sin{(wt)}\right] \\
\\
i_{C} &= C\frac{I_{0}\omega}{C\omega}\cos{(wt)} \\
\\
i_{C} &= I_{0}\cos{(wt)} \\
\end{aligned}
$$

#### 4. Graphing the LC Circuit Natural Response
![alt text](image-3.png)
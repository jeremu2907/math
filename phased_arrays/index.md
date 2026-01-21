[$\leftarrow$ Back](../index.html)
### Phased Arrays

#### Introduction

A phased array applies phase shifts accross array of antennas to steer the RX and TX beam (direction of maximum gain or main lobe) to a particular direction of interest. This article derives the time difference of arrival and phase-steering relationships used in far-field phased antenna arrays to estimate and control the direction of maximum gain.

#### Determining Incoming Wave Direction

We want to calculate the incoming angle of the wavefront in the following phased array set up.
![alt text](image.png)

We will be dealing with waves in the far field where they are approximated to be a plane wave. Here, the incoming angle will be denoted with $\theta$, the angle the wavefront velocity vector makes with the phased array plane normal vector. It can be shown, with geometric congruency, that the angle the wavefront makes with the antenna elements plane is also $\theta$.

We want to express $\theta$ as a function of values we can meaningfully measure. One such quantity is the time delay between antenna elements when they first detect the incoming wavefront. In the setup, the wavefront already reached antenna element 0 while still on its way to antenna element 1. Thus we will define our time delay as the time  it takes the wavefront to reach antenna element 1 the instance it reaches antenna element 0.

$$
\Delta t = t_{1} - t_{0}
$$

We start with the definition of velocity. To be precise, our velocity will have a magnitude equal to that of c, the speed of light, since our wave is an EM wave

$$
\begin{aligned}
v &= \frac{s}{t} \\\\
c &= \frac{d}{\Delta t}
\end{aligned}
$$

We can express $d$ differently by using trigonometry

$$
d = r\sin\theta
$$

Substituting into the velocity equation yields

$$
\begin{aligned}
c &= \frac{r\sin\theta}{\Delta t} \\\\
\frac{c \Delta t}{r} &= \sin\theta \\\\
\theta (\Delta t) &= \arcsin{\frac{c \Delta t}{r}}
\end{aligned}
$$

If the wavefront reaches antenna element 1 first then $\Delta t < 0$. Consequently, $\theta < 0$. This tells us which side the wavefront came from, at what angle.

This is called the **time difference of arrival** equation for a two-element phased array in the far field.

#### Beam Steering

Phased array applies a phase shift to an incoming or outgoing signal to antenna elements to steer the beam to the desired location.

We will calculate the phase shift, $\phi$, applied to each antenna so that it can steer a transmission beam to an angle $\theta$. A quantity we know before transmitting is the frequency of the wave, $f$.

##### Relative Phase Difference

Previously we used time as a measured quantity when we were passively receiving signals. This is not useful when we are actively transmitting or receiving over many frequencies. A fixed signal time delay would steer different frequencies to different angles. To avoid this, we need a quantity that, when fixed, steers all frequencies to the same angle. Relative phase difference is a frequency-normalized representation of time delay. At a fixed frequency, applying a phase shift is equivalent to applying a time delay.

A nice property of the phase is that it is proportional to the time delay. In fact, dividing our phase by $2 \pi$ is the exact same as dividing the time delay by our signal frequency's period, $T$

$$
\begin{aligned}
\frac{\phi}{2 \pi} &= \frac{\Delta t}{T} \\\\
\Delta t &= T \frac{\phi}{2 \pi}
\end{aligned}
$$

*Note that we can do the same using degree instead of using radians*

The period of a wave is the multiplicative inverse of its frequency
$$
T = \frac{1}{f}
$$

Substituting it into our time delay-phase equation yields

$$
\Delta t = \frac{1}{f} \frac{\phi}{2 \pi}
$$

##### Uniform Linear Array
An EM property that relates a wave's frequency, to its wavelength, $\lambda$ is

$$
c = \lambda f
$$

Substituting into the time difference of arrival equation yields

$$
\begin{aligned}
c &= \frac{r\sin\theta}{\Delta t} \\\\
\lambda f &= \frac{r\sin\theta}{\Delta t} \\\\
\Delta t &= \frac{r\sin\theta}{\lambda f}
\end{aligned}
$$

Substituting $\Delta t$ with the time delay-phase equation yields

$$
\begin{aligned}
\Delta t &= \frac{r\sin\theta}{\lambda f} \\\\
\frac{1}{f} \frac{\phi}{2 \pi} &= \frac{r\sin\theta}{\lambda f} \\\\
\phi &= \frac{2 \pi r \sin\theta}{\lambda}
\end{aligned}
$$

With an $n$-element array of even element separation, the phase applied to the $m^{th}$ element would simply be

$$
\phi = \frac{2 \pi r \sin\theta}{\lambda} m
$$

This is the **ULA steering law**.


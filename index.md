# Technical Notes
Jeremy Huynh
___
## Introduction
I kinda don't like that many learning sources never explain where a formula came from. *"Just plug the numbers in"* is the bane of my existence. If you ever feel the same way, you would understand my motivation. This site contains personal technical analysis of topics in engineering and physics as well as mathematical derivations. The purpose of this site is to define a problem and use fundamental mathematical principles to solve it, explaining the "*Where it came from*".

*This site is my passion manifested.*

___
## Content
- [Mathematics](#mathematics)
    - [Euler's Formula & Identity](#eulers-formula--identity)
    - [Solution to Nth Order Homogeneous ODE With Constant Coefficient](#nth-order-homogeneous-ode-with-constant-coefficient-solution)
- [Physics & Engineering](#physics-and-engineering)
    - [Natural Response of a Series LC Circuit](#natural-response-of-a-series-lc-circuit)
    - [Phased Arrays](#phased-arrays)
    - [IQ Sampling Circuit Analysis](#iq-sampling-circuit-analysis)

___
## Mathematics

### Euler's Formula & Identity
Using ODE to derive the generalized Euler's formula and the famous Euler's identity:
$$e^{i\pi} + 1 = 0$$

**[$\rightarrow$ Read more here](eulers_identity/index.html)**

### Nth Order Homogeneous ODE With Constant Coefficient Solution
A derivation of the general solution to the differential equation of the form

$$
y^{(n)} + a_1y^{(n - 1)} + a_2y^{(n - 2)} + ... + a_ny = 0
$$

is

$$
y = \sum_{k = 1}^{n}{C_{k1}e^{a_{k}x}\cos(b_{k}x) + C_{k2}e^{a_{k}x}\sin(b_{k}x)}
$$

**[$\rightarrow$ Read more here](ode_nth_order_homogeneous/index.html)**

___
## Physics and Engineering

### Natural Response of a Series LC Circuit
This section derives the natural response of a series LC circuit, showing how voltage and current oscillate sinusoidally at the natural frequency due to energy exchange between the inductor and capacitor.

![alt text](rc_circuit_natural_response/image-3.png)

**[$\rightarrow$ Read more here](rc_circuit_natural_response/index.html)**

### Phased Arrays
This secion derives the Uniform Linear Array steering law to be 

$$
\phi = \frac{2 \pi r \sin\theta}{\lambda} m
$$

using a simple two-element antenna array set up and far field EM wave approximations.

![alt text](phased_arrays/image.png)

**[$\rightarrow$ Read more here](phased_arrays/index.html)**

### IQ Sampling Circuit Analysis
This secion examines the exact operations that each cicuit component applies to an RF signal to produce IQ data.

![alt text](./iq_sampling/image.png)

**[$\rightarrow$ Read more here](./iq_sampling/index.html)**
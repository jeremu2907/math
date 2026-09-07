# Time-Varying and Time-Harmonic EM Fields

## 1. Maxwell's Equations

### Differential Form
$$
\begin{aligned}

\nabla \times \mathcal{E} &= -\mathcal{M}_i - \frac{\partial\mathcal{B}}{\partial t} \\
&= - \mathcal{M}_i - \mathcal{M}_d \\
&= - \mathcal{M}_t \\\\

\nabla \times \mathcal{H} &= \mathcal{J}_i + \mathcal{J}_c + \frac{\partial\mathcal{D}}{\partial t} \\
&=\mathcal{J}_{ic} + \frac{\partial\mathcal{D}}{\partial t} \\
&=\mathcal{J}_{ic} + \mathcal{J}_{d} \\
&=\mathcal{J}_{t} \\\\

\nabla \cdot \mathcal{D} &= q_{ev} \\\\
\nabla \cdot \mathcal{B} &= q_{mv}
\end{aligned}
$$

The field quantities above are time-varying and is a function of space and time, ie $\mathcal{E} = \mathcal{E}(x,y,z;t)$
- $\mathcal{E}$ = electric field intensity $(V/m)$
- $\mathcal{H}$ = magnetic field intensity $(A/m)$
- $\mathcal{D}$ = electric flux density $(C/m^2)$
- $\mathcal{B}$ = magnetic flux density $(Wb/m^2)$
- $\mathcal{J}_i$ = source electric current density $(A/m^2)$
- $\mathcal{J}_c$ = conduction electric current density $(A/m^2)$
- $\mathcal{J}_d$ = displacement electric current density $(A/m^2)$. If there is a changing electric field that causes a magnetic field (similar to that of a charging capacitor), then the equivalent electric current that causes the same magnetic field is the *displacement electric current*.
- $\mathcal{M}_i$ = source magnetic current density $(V/m^2)$
- $\mathcal{M}_d$ = displacement magnetic current density $(V/m^2)$
- $\mathcal{q}_{ev}$ = electric charge density $(C/m^3)$
- $\mathcal{q}_{mv}$ = magnetic charge density $(Wb/m^3)$

### Integral Form
$$
\begin{aligned}

\oint_C{\mathcal{E} \cdot dl} &= - \iint_S{\mathcal{M}_i \cdot d\mathcal{s}} - \frac{\partial}{\partial t}\iint_S{\mathcal{B}d\mathcal{s}} \\\\

\oint_C{\mathcal{H} \cdot dl} &= \iint_S{\mathcal{J}_{ic} \cdot d\mathcal{s}} + \frac{\partial}{\partial t}\iint_S{\mathcal{D} \cdot d\mathcal{s}} \\
&= \iint_S{\mathcal{J}_{ic} \cdot d\mathcal{s}} + \iint_S{\mathcal{J}_d \cdot d\mathcal{s}} \\\\

\iiint_V{\nabla \cdot \mathcal{D} dv} &= \iiint_V{q_{ev}dv}\\
&= \mathcal{Q}_e \\\\

\oiint_S{\mathcal{B} \cdot d\mathcal{s}} &= \mathcal{Q}_m \\\\

\oiint_S{\mathcal{J}_{ic} \cdot d\mathcal{s}} &= -\frac{\partial}{\partial t}\iiint_V{q_{ev}dv}\\
&= -\frac{\partial\mathcal{Q}_e}{\partial t}

\end{aligned}
$$

$\mathcal{Q}_e$ = total electric charge
$\mathcal{Q}_m$ = total magnetic charge

## 2. Constitutinve Params and Relations

Materials are made up of charges that interract with the EM field, thus changes the propagation behaviour of the fields, unlike in free space.

### Constitutive Params

- $\hat \epsilon$ = permittivity of the medium $(F/m)$ as a function of time
- $\hat \mu$ = permeability of the medium $(H/m)$ as a function of time
- $\hat \sigma$ = conductivity of the medium $(S/m)$ as a function of time

### Constitutive Relations

$$
\begin{aligned}

\mathcal{D} &= \hat \epsilon * \mathcal{E} \\\\

\mathcal{B} &= \hat \mu * \mathcal{H} \\\\

\mathcal{J}_c &= \hat \sigma * \mathcal{E}

\end{aligned}
$$

## 3. Boundary Conditions

- Maxwell's eqns in differential form solve or fields and their derivatives in continuous and bounded spaces.
- At discontinuity, the derivative of the field has no meaning. Therefore we must analyze the fields themselves, not their derivatives, using Maxwell's eqns in integral form. 
- Interfaces between mediums considered discontinuities, thus to analyze field behaviors at interfaces we use Maxwell's eqn integral form.
- An example is cell signal through walls.

### Finite Conductivity Media

Assume no E/M surface charges, at the interface between medias:
- The tangential $\mathcal{E}_x$ is continuous.
- The tangential $\mathcal{H}_x$ is continuous.
- The normal $\mathcal{D}_y$ is continuous.
- The normal $\mathcal{E}_y$ is discontinuous.
- The normal $\mathcal{B}_y$ is continuous.
- The normal $\mathcal{H}_y$ is discontinuous.

## 4. Power and Energy

We want a way to quantify the EM fields through space. To do this we want 

### Conservation of Energy
- Assume a volume $V$ enclosed in a surface $S$, the following equations are **conservation of energy** in integral and differential forms.

$$
\begin{aligned}
\oiint_S{(\mathcal{E} \times \mathcal{H}) \cdot d\bold{s}} + \iiint_V{[\mathcal{H} \cdot (\mathcal{M}_i + \mathcal{M}_d) + \mathcal{E} \cdot (\mathcal{J}_i + \mathcal{J}_c + \mathcal{J}_d)]dv} &= 0 \\\\

\nabla \cdot (\mathcal{E} \times \mathcal{H}) + \mathcal{H} \cdot (\mathcal{M}_i + \mathcal{M}_d) + \mathcal{E} \cdot (\mathcal{J}_i + \mathcal{J}_c + \mathcal{J}_d) &= 0
\end{aligned}
$$

### Poynting Vector
- The **Poynting Vector** $(W/m^2)$ is defined in the first integrand, which is:

$$
\mathcal{S} = \mathcal{E} \times \mathcal{H}
$$

### Conservation of Power
- $\mathcal{P}_e = \oiint_S{\mathcal{S} \cdot d\bold{s}}$: the total power exiting the volume $V$ $(W)$
- $\mathcal{P}_d = \iiint_V{\sigma \mathcal{E}^2dv}$: the total dissipated within the volume $V$ $(W)$
- $\mathcal{W}_e$ is the total electric energy $(J)$
- $\mathcal{W}_m$ is the total magnetic energy $(J)$
- $\mathcal{P}_s$: the total supplied power $(W)$ such that:
$$
\mathcal{P}_s = \mathcal{P}_e + \mathcal{P}_d + \frac{\partial}{\partial t}(\mathcal{W}_e + \mathcal{W}_m)
$$

## 5. Time-Harmonic Fields

We want to represent our vector fields in a frequency domain. We can extract the amplitude of our sinusoid signal per frequency. The frequencies lies in the domain and the corresponding amplitudes lies in the codomain. This representation of vector fields allow simpler operations.

### Frequency Domain

$$
\begin{aligned}

\mathcal{E}(x, y, z, t) &= \operatorname{Re}[\bold{E}(x, y, z) e^{j \omega t}] \\\\
\mathcal{H}(x, y, z, t) &= \operatorname{Re}[\bold{H}(x, y, z) e^{j \omega t}] \\\\
\mathcal{D}(x, y, z, t) &= \operatorname{Re}[\bold{D}(x, y, z) e^{j \omega t}] \\\\
\mathcal{B}(x, y, z, t) &= \operatorname{Re}[\bold{B}(x, y, z) e^{j \omega t}] \\\\
\mathcal{J}(x, y, z, t) &= \operatorname{Re}[\bold{J}(x, y, z) e^{j \omega t}] \\\\
\mathcal{q}(x, y, z, t) &= \operatorname{Re}[\bold{q}(x, y, z) e^{j \omega t}] \\\\

\end{aligned}
$$

### Maxwell's Equations
- Maxwell's equation in the frequency domain is the same as in [#1](#1-maxwells-equations)
- However because we are taking the time-derivative of $e^{j\omega t}$, the equations can be reduced to:

$$
\begin{aligned}

\nabla \times \bold{E} &= -\bold{M}_i - j \omega \bold{B} \\\\

\nabla \times \bold{H} &= \bold{J}_i + \bold{J}_c + j \omega \bold{D} \\\\

\nabla \cdot \bold{D} &= q_{ev} \\\\

\nabla \cdot \bold{B} &= q_{mv}
\end{aligned}
$$

### Poynting Vector
$$
\mathcal{S}_{av} = \bold{S} = \frac{1}{2}\operatorname{Re}[\bold{E} \times \bold{H}^*]
$$
$^*$ denotes the complex conjugate of a complex number
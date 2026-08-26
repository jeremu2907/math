## Maxwell's Equations

### Differential Form
$$
\begin{aligned}

\nabla \times \mathcal{E} &= -\mathcal{M}_i - \frac{\partial\mathcal{B}}{\partial t} \\
&= - \mathcal{M}_i - \mathcal{M}_d \\
&= - \mathcal{M}_t \\\\

\nabla \times \mathcal{H} &= \mathcal{I}_i + \mathcal{I}_c + \frac{\partial\mathcal{D}}{\partial t} \\
&=\mathcal{I}_{ic} + \frac{\partial\mathcal{D}}{\partial t} \\
&=\mathcal{I}_{ic} + \mathcal{I}_{d} \\
&=\mathcal{I}_{t} \\\\

\nabla \cdot \mathcal{D} &= q_{ev} \\\\
\nabla \cdot \mathcal{B} &= q_{mv}
\end{aligned}
$$

The field quantities above are time-varying and is a function of space and time, ie $\mathcal{E} = \mathcal{E}(x,y,z;t)$
$\mathcal{E}$ = electric field intensity $(V/m)$
$\mathcal{H}$ = magnetic field intensity $(A/m)$
$\mathcal{D}$ = electric flux density $(C/m^2)$
$\mathcal{B}$ = magnetic flux density $(Wb/m^2)$
$\mathcal{I}_i$ = source electric current density $(A/m^2)$
$\mathcal{I}_c$ = conduction electric current density $(A/m^2)$
$\mathcal{I}_d$ = displacement electric current density $(A/m^2)$. If there is a changing electric field that causes a magnetic field (similar to that of a charging capacitor), then the equivalent electric current that causes the same magnetic field is the *displacement electric current*.
$\mathcal{M}_i$ = source magnetic current density $(V/m^2)$
$\mathcal{M}_d$ = displacement magnetic current density $(V/m^2)$
$\mathcal{q}_{ev}$ = electric charge density $(C/m^3)$
$\mathcal{q}_{mv}$ = magnetic charge density $(Wb/m^3)$

### Integral Form
$$
\begin{aligned}

\oint_C{\mathcal{E} \cdot dl} &= - \iint_S{\mathcal{M}_i \cdot d\mathcal{s}} - \frac{\partial}{\partial t}\iint_S{\mathcal{B}d\mathcal{s}} \\\\

\oint_C{\mathcal{H} \cdot dl} &= \iint_S{\mathcal{I}_{ic} \cdot d\mathcal{s}} + \frac{\partial}{\partial t}\iint_S{\mathcal{D} \cdot d\mathcal{s}} \\
&= \iint_S{\mathcal{I}_{ic} \cdot d\mathcal{s}} + \iint_S{\mathcal{I}_d \cdot d\mathcal{s}} \\\\

\iiint_V{\nabla \cdot \mathcal{D} dv} &= \iiint_V{q_{ev}dv}\\
&= \mathcal{Q}_e \\\\

\oiint_S{\mathcal{B} \cdot d\mathcal{s}} &= \mathcal{Q}_m \\\\

\oiint_S{\mathcal{I}_{ic} \cdot d\mathcal{s}} &= -\frac{\partial}{\partial t}\iiint_V{q_{ev}dv}\\
&= -\frac{\partial\mathcal{Q}_e}{\partial t}

\end{aligned}
$$

$\mathcal{Q}_e$ = total electric charge
$\mathcal{Q}_m$ = total magnetic charge
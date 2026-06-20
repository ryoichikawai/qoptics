# Model

## Two-level system

Consider an atom of two energy levels, a ground state $| g\rangle$ of energy $E_{g}$ and  an excited state $|e\rangle$ of energy $E_{e}$.  Lowering and raising operators are defined respectively by

$$
\sigma_{-} = |g\rangle\langle e|, \quad \sigma_{+} = |e\rangle\langle g|
$$

The standard Pauli operators are defined as

$$
\sigma_{1} = \sigma_{+}+\sigma_{-}, \quad \sigma_{2} = -i \left(\sigma_{+}-\sigma_{-}\right), \quad \sigma_{3} = |e\rangle\langle e| - |g\rangle\langle g|
$$

The Hamiltonian of the two-level system is

$$
H_{s} = \frac{\hbar}{2} \omega_{0} \sigma_{3}
$$

where $\hbar\omega_{0}=E_{e}-E_{g}$ is the excitation energy .



## External driving

The atom is driven by a laser beam, which we consider as classical electromagnetic fields.  Assuming that the wave length of the laser beam is much larger than the size of the atom,  the electric field of the laser beam experienced by the atom can be written as

$$
\vec{E}(t) = \vec{E}_{0} \cos(\omega_{L} t) 
$$

where the phase of oscillation is set to $0$.  Then, the driving Hamiltonian is modeled by

$$
H_{L} = - \hbar\Omega \cos(\omega_{L} t) \sigma_1
$$

With the dipole moment of atomic excitation $\vec{d}$ ,  $\Omega \equiv \vec{d}\cdot \vec{E}$ .

## Rotating wave approximation

The total Hamiltonian is 

$$
H_{S} + H_{L} = \frac{\hbar}{2} \omega_0 \sigma_{3} - \hbar\Omega \cos(\omega_{L} t) \sigma_1
$$

We adopt the standard rotating wave approximation.  Then, the total Hamiltonian is simplified to

$$
H_{rwa} = \frac{\hbar}{2}{\Delta} \sigma_{3} + \frac{\hbar}{2} \Omega \sigma_{1}
$$

where $\Delta = \omega_{0} - \omega_{L}$ is detuning of the input laser.

## Interaction with the environment

The environment is assumed to be a photon gas in a thermal equilibrium at temperature $T$. We take into account the interaction between the atom and the environments with the formalism of linear quantum master equation (a Lindblad form of quantum master equation).  The dissipator is defined by

$$
\mathcal{D}(\rho) = \gamma_{0} (N+1) \left(\sigma_{-}\rho\sigma_{+} - \frac{1}{2} \sigma_{+}\sigma_{-}\rho - \frac{1}{2} \rho \sigma_{+}\sigma_{-} \right)\\+\gamma_{0} N \left(\sigma_{+}\rho\sigma_{-} - \frac{1}{2} \sigma_{-}\sigma_{+}\rho - \frac{1}{2} \rho \sigma_{-}\sigma_{+\\} \right)
$$

where $\rho$ is the density operator of the atom, and

$$
\gamma_{0} = \frac{4 \omega_{0}^{3} |\vec{d}|^2}{3\hbar c^3}, \qquad N=\frac{1}{e^{\hbar \omega_0/T}-1}.
$$

## Quantum master equation

The  time evolution of the atomic state $\rho$ follows the quantum master equation

$$
\frac{d}{dt} \rho = -\frac{i}{\hbar} \left[H_{S}+H_{L},\rho\right]+ \mathcal{D}(\rho)
$$
Here we ignored the Lamb shift and the Stark shift.

_Some simple cases_

* For spontaneous radiation,  set $\Omega=\omega_{L}=0$.

* For resonant fluorescence,  set $\Delta=0$.


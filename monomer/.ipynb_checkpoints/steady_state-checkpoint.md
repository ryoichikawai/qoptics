# Steady state solution

Now we solve the quantum master equation.  Under the presence of dissipation, the system is expected to approach a steady state.  Our goal is to find the steady state.  The quantum master equations is an ordinary differential equation for a density matrix.  It is not difficult to solve it numerically.  For two-dimensional Hilbert space, the equation can be solved analytically.  There is a beautiful method known as the Bloch equation.  However, it works only for two-dimensional Hilbert space.  We first solve the master equation for matrix elements, extension to the higher dimension is in mind.  Then, solve it again using the Bloch equation.

Here after, we assume $\hbar=1$.

## Matrix elements

The density matrix can be expressed in $2\times2$ matrix.  Using $|g\rangle$ and $|e\rangle$ as basis set, the matrix elements are $\rho_{gg} = \langle g|\rho|g\rangle$, $\rho_{ee}=\langle e|\rho|e\rangle$, $\rho_{eg} = \langle e |\rho| g\rangle$, and $\rho_{ge} = \langle{g}|\rho|e\rangle$.  The master equation is just a coupled ODEs.  Since the off-diagonal elements are complex, it is a coupled ODEs of six real functions.  However, not all six functions are independent.  Using the normalization $\rho_{gg}+\rho_{ee}= 1$,  we can get rid of one matrix element. Furthermore, the density matrix is self-adjoint, and thus $\rho_{eg}=\rho_{ge}^{*}$.    Hence, only two matrix elements are independent.  For example, it is enough to compute $\rho_{ee}$ and $\rho_{eg}$. We need only three differential equations for real functions, $Z\equiv\rho_{ee}$, $X\equiv\text{Re}~\rho_{eq}$ and $Y\equiv\text{Im}~\rho_{eg}$.  Then, the matrix  elements are given by $\rho_{gg}=1-Z$, $\rho_{ee}=Z$, $\rho_{eg}=X+iY$, and $\rho_{ge}=X-iY$.  The equations for $X$, $Y$, and $Z$ are


$$
\frac{d}{dt} X = -\frac{\gamma}{2} X - \Delta Y \\
\frac{d}{dt} Y = -\frac{\gamma}{2} Y - \Delta X - \frac{\Omega}{2} (1-2Z)\\
\frac{d}{dt} Z = - \gamma Z + \Omega Y + \frac{\gamma-\gamma_0}{2}
$$

where $\gamma = \gamma_0 (2N+1)$.

Since we are interested in the steady state, we omit time derivatives.  We obtain a simple linear equation:

$$
\frac{\gamma}{2} X + \Delta  Y = 0\\
\Delta X + \frac{\gamma}{2} Y - \Omega Z = -\frac{\Omega}{2}\\
-\Omega Y + \gamma Z  = \frac{\gamma-\gamma_0}{2}
$$

Writing it in a matrix form:

$$
\begin{bmatrix}
\frac{\gamma}{2} & \Delta & 0 \\
\Delta & \frac{\gamma}{2} & - \Omega \\
0 & \Omega & \gamma 
\end{bmatrix}
\begin{bmatrix}
X \\ Y \\ Z
\end{bmatrix}
= 
\begin{bmatrix}
0 \\ -\frac{\Omega}{2} \\ 
\frac{\gamma-\gamma_0}{2}
\end{bmatrix}
$$

Hence, the steady state is simply

$$
\begin{bmatrix}
X^{ss} \\ Y^{ss} \\ Z^{ss}
\end{bmatrix}
= 
\begin{bmatrix}
\frac{\gamma}{2} & \Delta & 0 \\
\Delta & \frac{\gamma}{2} & - \Omega \\
0 & \Omega & \gamma 
\end{bmatrix}^{-1}
\begin{bmatrix}
0 \\ -\frac{\Omega}{2} \\ 
\frac{\gamma-\gamma_0}{2}
\end{bmatrix}
$$


We first solve simple cases.

### Case 1: Thermal state

When no external drive is applied, the system relax to a thermal equilibrium.  Let $\Delta=0$ and $\Omega=0$, The steady steady state solution is

$$
\begin{bmatrix}
X^{ss} \\ Y^{ss} \\ Z^{ss}
\end{bmatrix}
= 
\begin{bmatrix}
\frac{\gamma}{2} & 0 & 0 \\
0 & \frac{\gamma}{2} & 0 \\
0 & 0 & \gamma 
\end{bmatrix}^{-1}
\begin{bmatrix}
0 \\ 0 \\ 
\frac{\gamma-\gamma_0}{2}
\end{bmatrix}
= \begin{bmatrix}
\frac{2}{\gamma} & 0 & 0 \\
0 & \frac{2}{\gamma} & 0 \\
0 & 0 & \frac{1}{\gamma} 
\end{bmatrix}
\begin{bmatrix}
0 \\ 0 \\ 
\frac{\gamma-\gamma_0}{2}
\end{bmatrix}
=\begin{bmatrix}
0 \\ 0 \\ 
\frac{\gamma-\gamma_0}{2\gamma}
\end{bmatrix}
$$

$X^{ss}=Y^{ss}=0$ imply $\rho_{eg}^{ss}=\rho_{ge}^{ss}=0$.  $Z^{ss}=\rho_{ee}^{ss} = \frac{\gamma-\gamma_0}{2\gamma} = \frac{N}{2N+1} = \frac{1}{e^{\omega_0/T}+1}$, which is the probability of finding the atom in the excited state under the thermal equilibrium.  The last matrix element is $\rho_{gg} = 1-\rho_{ee} = \frac{e^{\omega_0/T}}{e^{\omega_0/T}+1}$.

### Case 2: resonant fluorescence

The external drive is tuned to the excitation energy, and thus $\Delta=0$.  Then, the equation becomes

$$
\begin{bmatrix}X^{ss} \\ Y^{ss} \\ Z^{ss}\end{bmatrix}= \begin{bmatrix}\frac{\gamma}{2} & 0 & 0 \\0 & \frac{\gamma}{2} & -\Omega \\0 & \Omega & \gamma \end{bmatrix}^{-1}\begin{bmatrix}0 \\ -\frac{\Omega}{2} \\ \frac{\gamma-\gamma_0}{2}\end{bmatrix}
$$

$X^{ss}$ is independent from $Y^{ss}$ and $Z^{ss}$  and thus $X^{ss}=0$.  Thus we need to find only the inverse of $2x2$ matrix

$$
\begin{bmatrix}
Y^{ss} \\ Z^{ss}
\end{bmatrix}=
\begin{bmatrix}
\frac{\gamma}{2} & - \Omega \\ \Omega & \gamma
\end{bmatrix}^{-1}
\begin{bmatrix}
-\frac{\Omega}{2} \\ \frac{\gamma-\gamma_0}{2}
\end{bmatrix}
= \frac{1}{\gamma^2/2+\Omega^2} 
\begin{bmatrix}
\gamma  & \Omega \\ -\Omega & \frac{\gamma}{2}
\end{bmatrix}
\begin{bmatrix}
-\frac{\Omega}{2} \\ \frac{\gamma-\gamma_0}{2}
\end{bmatrix}
$$

The solution is

$X^{ss}=0$, $Y^{ss}=-\frac{\gamma_0 \Omega}{\gamma^2+2\Omega^2}$, and $Z^{ss}=\frac{1}{2} \frac{2 \Omega^2 + \gamma (\gamma-\gamma_0)}{\gamma^2 + 2 \Omega^2}$.  We have the matrix elements

$$
\rho_{ee}^{ss} = \frac{1}{2} \frac{2 \Omega^2 + \gamma (\gamma-\gamma_0)}{\gamma^2 + 2 \Omega^2}\\
\rho_{gg}^{ss} = \frac{1}{2} \frac{2 \Omega^2 + \gamma(\gamma+\gamma_0)}{\gamma^2+2 \Omega^2} \\
\rho_{eg}^{ss}= -i \frac{\gamma_0 \Omega}{\gamma^2+2\Omega^2} \\
\rho_{ge}^{ss}= + i \frac{\gamma_0 \Omega}{\gamma^2+2\Omega^2}
$$


### Case 3: Off-resonance fluorescence

Now, we have to invert the full matrix, which can be done but needs a bit of algebra.  The result is

$$
\begin{bmatrix}
\frac{\gamma}{2} & \Delta & 0 \\
\Delta & \frac{\gamma}{2} & - \Omega \\
0 & \Omega & \gamma 
\end{bmatrix}^{-1}=
\frac{1}{\gamma(\gamma^2+2\Omega^2-4\Delta^2)}
\begin{bmatrix}
2(\gamma^2+2\Omega^2) & -4\gamma\Delta & -4 \Delta \Omega\\
-4\gamma\Delta & 2 \gamma^2 & 2\gamma\Omega\\
4 \Delta\Omega & 2 \gamma\Omega & \gamma^2-4\Delta^2
\end{bmatrix}
$$

The rest is simple matrix calculations.  The steady state is found to be

$$
X^{ss} = \frac{2 \Delta \gamma_0 \Omega}{\gamma(\gamma^2+2\Omega^2-4 \Delta^2)}\\
Y^{ss} = -\frac{\gamma_0 \Omega}{\gamma^2 + 2 \Omega^2 - 4 \Delta^2}\\
Z^{ss} = \frac{\gamma\left(\gamma(\gamma-\gamma_0) + 2 \Omega^2\right)-4 \Delta^2(\gamma-\gamma_0)}{2\gamma\left(\gamma^2+2\Omega^2-4 \Delta^2\right)}
$$

and the corresponding matrix elements are

$$
\rho_{gg}=\frac{\gamma\left(\gamma(\gamma+\gamma_0) + 2 \Omega^2\right)-4 \Delta^2(\gamma+\gamma_0)}{2\gamma\left(\gamma^2+2\Omega^2-4 \Delta^2\right)}\\
\rho_{ee}=\frac{\gamma\left(\gamma(\gamma-\gamma_0) + 2 \Omega^2\right)-4 \Delta^2(\gamma-\gamma_0)}{2\gamma\left(\gamma^2+2\Omega^2-4 \Delta^2\right)}\\
\rho_{eg}=\frac{\gamma_0 \Omega (2\Delta - i \gamma)}{\gamma(\gamma^2+2\Omega^2-4\Delta^2)}\\
\rho_{ge}=\frac{\gamma_0 \Omega (2\Delta + i \gamma)}{\gamma(\gamma^2+2\Omega^2-4\Delta^2)}
$$


From this result, we can recover the previous case  by substituting $\Delta=0$.


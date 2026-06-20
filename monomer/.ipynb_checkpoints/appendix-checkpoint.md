# Appendix



## Solution for resonant fluorescence

​	First, we find a steady state directly without solving the ODE

We use the variable elimination method to solve
$$
\frac{d}{dt} Y = -\frac{\gamma}{2} Y - \Omega (1-2Z)\\
\frac{d}{dt} Z = - \gamma Z - \frac{\Omega}{2} Y + \frac{\gamma-\gamma_0}{2}
$$
From the second equation,
$$
Y = -\frac{2}{\Omega}\left[\frac{dZ}{dt} + \gamma Z - \frac{\gamma-\gamma_0}{2} \right]
$$
Substituting this to the first equation,
$$
-\frac{2}{\Omega}\left[\frac{d^2Z}{dt^2} + \gamma \frac{dZ}{dt}\right] = + \frac{\gamma}{\Omega}\left[\frac{dZ}{dt} + \gamma Z - \frac{\gamma-\gamma_0}{2} \right] - \Omega (1-2Z)
$$
Rearranging it, we obtain
$$
\frac{d^2Z}{dt^2} + \frac{3\gamma}{2}  \frac{dZ}{dt} - (\gamma^2/2 + \Omega^2) Z = \frac{\Omega^2}{2}
$$
This is a second-order inhomogeneous ODE of constant coefficients, which can be solved with a standard method.
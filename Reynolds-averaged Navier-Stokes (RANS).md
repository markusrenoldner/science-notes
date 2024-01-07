# Reynolds-averaged Navier-Stokes (RANS)
also called Reynolds-equations

Since for turbulent flows with technically relevant Reynolds numbers the Navier-Stokes equations cannot be solved numerically with reasonable effort (see [[Computational cost estimate of DNS of turbulent flows in CFD]]), the quantities are divided into a mean value and a fluctuation value. Here, the mean value is chosen so that the fluctuation has the mean value zero.

In cartesian coordinates:
$$
\rho \frac{\partial \bar{u}_i}{\partial t}+\rho\left(\frac{\partial \bar{u}_i \bar{u}_j}{\partial x_j}\right)=\bar{f}_i-\frac{\partial \bar{p}}{\partial x_i}+\frac{\partial}{\partial x_j}(\eta\left(\frac{\partial \bar{u}_i}{\partial x_j}+\frac{\partial \bar{u}_j}{\partial x_i}\right)-\rho \underbrace{\overline{u_i^{\prime} u_j^{\prime}}}_{R S T})
$$
which is basically the [[Navier-Stokes equations]] with an extra term: the Reynolds stress tensor.


## Derivation:

In the incompressible Navier-Stokes equations
1. the instantaneous values of the velocity components and the pressure are replaced by the respective sum of mean value and statistical variation:
$$
\begin{aligned}
& u_i=\overline{u_i}+u_i^{\prime} \\
& p=\bar{p}+p^{\prime}
\end{aligned}
$$
2. and Density and viscosity fluctuations are neglected:
$$
\begin{aligned}
& \frac{\partial \rho}{\partial t}=0 \Leftrightarrow \rho=\text { konst. } \\
& \frac{\partial \eta}{\partial t}=0 \Leftrightarrow \eta=\text { konst. }
\end{aligned}
$$
The momentum equation of the [[Navier-Stokes equations]] in cart. coord. gives
$$
\rho \frac{\partial u_i}{\partial t}+\rho\left(\frac{\partial u_i u_j}{\partial x_j}\right)=f_i-\frac{\partial p}{\partial x_i}+\eta \frac{\partial}{\partial x_j}\left(\frac{\partial u_i}{\partial x_j}+\frac{\partial u_j}{\partial x_i}\right)
$$
here noted in Einstein's summation convention.

The incompressible Reynolds-averaged momentum equation is then:
$$
\rho \frac{\partial \bar{u}_i}{\partial t}+\rho\left(\frac{\partial \bar{u}_i \bar{u}_j}{\partial x_j}\right)=\bar{f}_i-\frac{\partial \bar{p}}{\partial x_i}+\frac{\partial}{\partial x_j}\left[\eta\left(\frac{\partial \bar{u}_i}{\partial x_j}+\frac{\partial \bar{u}_j}{\partial x_i}\right)-\rho \underbrace{\overline{u_i^{\prime} u_j^{\prime}}}_{R S T}\right]
$$
The new term resulting from the averaging follows from the non-negligible velocity correlation: $\overline{u_i^{\prime} u_j^{\prime}}$. This tensor is called the Reynolds stress tensor (RST).


## Source:
https://de.wikipedia.org/wiki/Reynolds-Gleichungen
https://en.wikipedia.org/wiki/Reynolds-averaged_Navier%E2%80%93Stokes_equations
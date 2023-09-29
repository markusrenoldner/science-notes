[[Differential equations]]

An extension of [[Shallow water equations]] that combines the original fluid problem with [[Plasma physics]].

They take into account the effect of the magnetic field studying the global dynamics of the solar tachocline. The two-dimensional SWMHD equations with non-flat bottom topography give the following hyperbolic conservation law:
$$
\partial_t\boldsymbol{U} +\partial_{x1} \boldsymbol{F} + \partial_{x2} \boldsymbol{F} =-\boldsymbol{G}(\boldsymbol{U}),
$$
#todo that is wrong^


with the divergence-free condition
$$
\nabla \cdot(h \boldsymbol{B})=0
$$
where $\boldsymbol{U}$ is the conservative variables vector,
and $\boldsymbol{F}_1$, $\boldsymbol{F}_2$ are flux vectors along the $x_1$ - and $x_2$ directions and defined by
$$
\begin{aligned}
\boldsymbol{U} & =\left(h, h \boldsymbol{v}^{\mathrm{T}}, h \boldsymbol{B}^{\mathrm{T}}\right)^{\mathrm{T}}, \\
\boldsymbol{F}_{\ell} & =\left(h v_{\ell}, h v_{\ell} \boldsymbol{v}^{\mathrm{T}}-h B_{\ell} \boldsymbol{B}^{\mathrm{T}}+\frac{1}{2} g h^2 \boldsymbol{e}_{\ell}^{\mathrm{T}}, h\left(v_{\ell} \boldsymbol{B}-B_{\ell} \boldsymbol{v}\right)^{\mathrm{T}}\right)^{\mathrm{T}},\quad \ell=1,2, \\
\boldsymbol{G} & =\left(0, g h \nabla b, \mathbf{0}_2^{\mathrm{T}}\right)^{\mathrm{T}}, \quad \mathbf{0}_2^{\mathrm{T}}=(0,0),
\end{aligned}
$$
with the height of the conducting fluid $h$
the fluid velocity vector $\boldsymbol{v}=\left(v_1, v_2\right)^{\mathrm{T}}$
the magnetic field vector $\boldsymbol{B}=\left(B_1, B_2\right)^{\mathrm{T}}$
the gravitational acceleration constant $g$
the bottom topography $b=b(x, y)$
and $\boldsymbol{e}_{\ell}$ denotes the $\ell$ th column of the $2 \times 2$ unit matrix.


## System in 5 variables
The system could also be written out in 5 variables:
$$
\begin{aligned}
\boldsymbol{U} & =\left(h, h v_1,h v_2, h B_1,h B_2\right), \\
\boldsymbol{F}_{\ell} & =\left(h v_{\ell}, h v_{\ell} \boldsymbol{v}^{\mathrm{T}}-h B_{\ell} \boldsymbol{B}^{\mathrm{T}}+\frac{1}{2} g h^2 \boldsymbol{e}_{\ell}^{\mathrm{T}}, h\left(v_{\ell} \boldsymbol{B}-B_{\ell} \boldsymbol{v}\right)^{\mathrm{T}}\right)^{\mathrm{T}},\quad \ell=1,2, \\
\boldsymbol{G} & =\left(0, g h \nabla b, \mathbf{0}_2^{\mathrm{T}}\right)^{\mathrm{T}}, \quad \mathbf{0}_2^{\mathrm{T}}=(0,0),
\end{aligned}
$$
#todo 


## Source
P. A. Gilman, Magnetohydrodynamic “shallow water” equations for the solar tachocline, Astrophys. J., 544 (2000), pp. L79–L82
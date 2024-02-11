# Laplace operator in polar coordinates in 2D


The goal is to transform the 2D Laplace operator
$$\Delta u = u_{xx}+u_{yy}$$
to polar coordinates, i.e. we express the operator in new coordinates $r$ and $\phi$ defined by
$$\begin{aligned}
x&=r\cos(\phi) \\ y&= r\sin(\phi)
\end{aligned}$$
First, we compute the first partial derivatives of $u$
$$\begin{aligned}
\frac{\partial u}{\partial r} &= \frac{\partial u}{\partial x} \frac{\partial x}{\partial r} + \frac{\partial u}{\partial y} \frac{\partial y}{\partial r} = \cos(\phi)\frac{\partial u}{\partial x}+\sin(\phi) \frac{\partial u}{\partial y}\\

\frac{\partial u}{\partial \phi} &= \frac{\partial u}{\partial x} \frac{\partial x}{\partial \phi} + \frac{\partial u}{\partial y} \frac{\partial y}{\partial \phi} = -\sin(\phi)\frac{\partial u}{\partial x}+\cos(\phi) \frac{\partial u}{\partial y}
\end{aligned}$$
and the second partial derivatives
$$\begin{aligned}
\frac{\partial^2 u}{\partial r^2} &= \cos(\phi)\frac{\partial}{\partial r} \frac{\partial u}{\partial x} + \sin(\phi)\frac{\partial}{\partial r} \frac{\partial u}{\partial y} \\ 
&= \cos(\phi)\left(\frac{\partial}{\partial x}\frac{\partial x}{\partial r} \frac{\partial u}{\partial x} + \frac{\partial}{\partial y}\frac{\partial y}{\partial r} \frac{\partial u}{\partial x} \right) + \sin(\phi)\left(\frac{\partial}{\partial x}\frac{\partial x}{\partial r} \frac{\partial u}{\partial y} + \frac{\partial}{\partial y}\frac{\partial y}{\partial r} \frac{\partial u}{\partial y} \right)\\
&= \cos^2(\phi)\frac{\partial^2 u}{\partial x^2} + 2\cos(\phi) \sin(\phi) \frac{\partial^2 u}{\partial y\partial x} + \sin^2(\phi)\frac{\partial^2 u}{\partial y^2} \\
\frac{\partial^2 u}{\partial \phi^2} &= \dots \\
&= -r\cos(\phi) \frac{\partial u}{\partial x} + r^2 \sin^2(\phi) \frac{\partial^2 u }{\partial x^2} - 2r^2\sin(\phi)\cos(\phi) \frac{\partial^2 u }{\partial x \partial y} -r\sin(\phi) \frac{\partial u}{\partial y} +r^2\cos^2(\phi)\frac{\partial^2 u }{\partial y^2}
\end{aligned}$$
Now one can "play around" with the terms to try to find an expression for $u_{xx}+u_{yy}$. E.g. summing the second partial derivatives (with a scaling factor to get rid of the $r^2$ terms) gives
$$\begin{aligned}
\frac{\partial^2 u}{\partial r^2}+\frac{1}{r^2}\frac{\partial^2 u}{\partial \phi^2} &= \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} -\frac{1}{r}\left(\cos(\phi)\frac{\partial u}{\partial x} + \sin(\phi)\frac{\partial u}{\partial y} \right) 
\end{aligned} $$
This already looks excellent, as the last term on the right is exactly $\displaystyle \frac{1}{r}\frac{\partial u}{\partial r}$ which gives
$$\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = \frac{\partial^2 u}{\partial r^2}+\frac{1}{r^2}\frac{\partial^2 u}{\partial \phi^2} + \frac{1}{r}\frac{\partial u}{\partial r}$$


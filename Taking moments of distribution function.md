# Taking moments of distribution function
[[Statistical mechanics]]
[[Plasma physics]]

## Definition using Riemann integral:
The $n^{th}$ moment of a variable $x$ for the distribution function $f(x)$ is 
$$
    \left \langle x^n \right \rangle \equiv \int_\mathbb{R} x^n f(x) dx
$$

## Example 1 of average particle speeds in plasma:  $\left\langle v_x^2\right\rangle$

Assume a "Maxwellian-distribution" of velocities for particle $\alpha$ with velocity $\boldsymbol{v}$ is:
$$
f_\alpha(\boldsymbol{v})=\left(\frac{m_\alpha}{2 \pi T_\alpha}\right)^{3 / 2} \exp \left(-\frac{m_\alpha}{2 T_\alpha} \boldsymbol{v}^2\right)
$$
With the thermal velocity $v_{t h, \alpha}=\sqrt{\frac{T_\alpha}{m_\alpha}}$, we get
$$
f_\alpha=\frac{1}{(2 \pi)^{3 / 2}} \frac{1}{v_{t h, \alpha}^3} \exp \left(-\frac{\boldsymbol{v}^2}{2 v_{t h, \alpha}^2}\right)
$$
Using this definition, it's possible to write the integral for the average value of $v_x^2$ :
$$
\begin{aligned}
\left\langle v_x^2\right\rangle & =\frac{1}{(2 \pi)^{3 / 2}} \frac{1}{v_{t h, \alpha}^3} \int_\mathbb{R} v_x^2 e^{-\frac{v_x^2+v_y^2+v_z^2}{2 v_{t h, \alpha}^2}} d v_x d v_y d v_z= \\
& =\frac{1}{(2 \pi)^{3 / 2}} \frac{1}{v_{t h, \alpha}^3} \int_\mathbb{R} v_x^2 e^{-\frac{v_x^2}{2 v_{t h, \alpha}^2}} d v_x 
\int_\mathbb{R} e^{-\frac{v_y^2}{2 v_{t h, \alpha}^2}} d v_y
\int_\mathbb{R} e^{-\frac{v_z^2}{2 v_{t h, \alpha}^2} d v_z}
\end{aligned}
$$

These are "Gauss integrals", and can be solved analytically. The result is the root-mean-square (RMS) velocity:
$$
\left\langle v_x^2\right\rangle=v_{t h, \alpha}^2 \quad \Rightarrow \quad \sqrt{\left\langle v_x^2\right\rangle}=v_{t h, \alpha}
$$


## Example 2 of average particle speeds in plasma:  $\left\langle\boldsymbol{v}^2\right\rangle$

We can use the previous example to find $\left\langle\boldsymbol{v}^2\right\rangle$. Since:
$$
\boldsymbol{v}^2=\boldsymbol{v}\cdot \boldsymbol{v}=v_x^2+v_y^2+v_z^2
$$
and $v_x, v_y, v_z$ are independent variables, we have:
$$
\left\langle v^2\right\rangle=\left\langle v_x^2+v_y^2+v_z^2\right\rangle=\left\langle v_x^2\right\rangle+\left\langle v_y^2\right\rangle+\left\langle v_z^2\right\rangle=3\left\langle v_x^2\right\rangle=3 v_{t h, \alpha}^2
$$
and thus:
$$
\sqrt{\left\langle v^2\right\rangle}=\sqrt{3} v_{t h, \alpha}
$$



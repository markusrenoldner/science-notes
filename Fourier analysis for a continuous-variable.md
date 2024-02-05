# Fourier analysis for a continuous-variable
[[Analysis]]

Summary of Fourier analysis results for functions of a continuous variable $x\in\mathbb{R}$.
Does not cover the discrete Fourier transform for functions of a discrete variable $x\in\mathbb{Z}$!

## Fourier series

**Requirements on $f$** ("Dirichlet conditions for Fourier series)
 - $f$ is periodic over a finite $I\equiv[x_0,x_0+L]\subset\mathbb{R}$
- $f$ is single valued, cont. except at finite number of points, and has finite number of extrema in $I$
- $f\in L^1(I)$ meaning that $\int_I |f| \leq \infty$

If these requirements are fulfilled, one can rewrite $f(x)$ as a **Fourier series**, i.e.
$$\begin{aligned}

f(x)&=\sum_{k=-\infty}^\infty c_k \exp{\left ( \frac{2\pi ikx}{L} \right )}\\

c_k &= \frac{1}{L}\int_I f(x) \exp{\left ( -\frac{2\pi ikx}{L} \right )}dx

\end{aligned}$$

## Fourier transformation

**Requirements on $f$**
$$f\in L^1(\mathbb{R})\quad\iff\quad \int_\mathbb{R} |f| \leq \infty$$

Now define the **Fourier transform**
$$\begin{aligned}

\mathcal{F}[f](w)\equiv \tilde f(\omega) &\equiv \frac{1}{\sqrt{2\pi}} \int_\mathbb{R} f(x) e^{-i\omega x} dx \\

\mathcal{F}^{-1}[\tilde f](x) \equiv f(x) &\equiv \frac{1}{\sqrt{2\pi}}\int_{\mathbb{R}} \tilde f(\omega) e^{i\omega x}d\omega

\end{aligned}$$
**Derivation:** Introduce a new variable (the frequency) by
$$\begin{aligned}

\omega_k &\equiv \frac{2\pi k}{L},\\

\Delta \omega &\equiv \omega_{k}-\omega_{k-1}=\frac{2\pi k-(k-1)}{L}=\frac{2\pi}{L}\\

\frac{\Delta \omega}{2\pi}&=\frac{1}{L}

\end{aligned}$$
Now we use the Fourier series with the definition of $\omega_k$
$$\begin{aligned}

f(x)&=\sum_{k=-\infty}^\infty c_k e^{i\omega_k x}\\

&= \sum_{k=-\infty}^\infty \frac{\Delta\omega}{2\pi} e^{i\omega_k x}\int_I f(x) e^{-i\omega_k x}dx

\end{aligned}$$
We assume $L\to\infty$ or $\omega_k\to 0$ to replace the Riemann sum by an integral i.e. $f$ is not periodic on a finite interval:
$$\begin{aligned}
f(x)&=\lim_{\Delta \omega\to 0} \sum_{k=-\infty}^\infty \frac{\Delta\omega}{2\pi} e^{i\omega_k x}\int_I f(x) e^{-i\omega_k x}dx\\
&=\frac{1}{2\pi} \int_\mathbb{R} e^{i\omega x}\left [ \int_\mathbb{R} f(x) e^{-i\omega x}dx \right ] d\omega\\
&=\frac{1}{\sqrt{2\pi}} \int_\mathbb{R} e^{i\omega x}\underbrace{ \left [\frac{1}{\sqrt{2\pi}}\int_\mathbb{R} f(x) e^{-i\omega x}dx\right ]}_{\equiv\mathcal{F}[f](\omega)} d\omega
\end{aligned}$$
In the last step we have identified the Fourier transform.

## Notation for frequency $k$

if $k$ is the frequency in space, and $\omega$ the one in time, one should rename the summation index to e.g. $j$:
$$f(x)=\sum_{j=-\infty}^\infty c_j \exp{\left ( \frac{2\pi ijx}{L} \right )}=\sum_{j=-\infty}^\infty c_j \exp{\left ( ik_j x \right )}$$
and in time:
$$f(t)=\sum_{j=-\infty}^\infty c_j \exp{\left ( \frac{2\pi ijt}{T} \right )}=\sum_{j=-\infty}^\infty c_j \exp{\left ( i\omega_j t \right )}$$

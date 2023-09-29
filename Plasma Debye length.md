
Assume neutrality ($n_e=n_i$), and use Gauss' law ([[Maxwell equations]]), the equation of motion of an electron in an electric field/electric potential $\Phi$, and a Taylor expansion and linearization to get an equation for the potential:
$$\nabla^2 \Phi =- \frac{1}{\epsilon_{0}} q_T\delta(\vec{r}) + \frac{1}{\lambda_{Dl}^2}\Phi$$
with the electron Debye length defined as
$$\lambda_{Dl} := \sqrt{\frac{\epsilon_{0}T_{e}}{e^2n_0}}$$
The reason why the linearization makes sense is explained in [1]. The equation before can be solved in spherical coordinates:
$$\Phi(r) = \frac{1}{4\pi \epsilon_{0}}\frac{q_{T}}{r} \text{ exp}(-r/\lambda_{Dl})$$
in green we see the Coulomb potential without the exponential term, in green the derived equation above with exponential term. If $r$ approaches the order of magnitude of the Debye length, the potential deviates from that, see in red.
![[MHD-potential-testcharge.png]]
The plasma therefore "screens" the potential of the charged particle ("Debye screened potential"). In this derivation, we have assumed, that the number of particles in a Debye cube $N_D:=n\lambda_{Dl}^{3}$ is "large".

Conclusions:
- deviation from quasi-neutrality ($n_{e\neq}n_0$) occurs at $r<\lambda_{Dl}$
- One-to-one interactions are therefore weak if $N_D$ is "large", as then the potential between two particles is small (see result of previous bullet point).



## Sources
1. EPFL - Introduction to Plasma Physics, lecture 1b)
2. https://de.wikipedia.org/wiki/Debye-L%C3%A4nge
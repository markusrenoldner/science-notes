
[[Electrodynamics]]

#todo 

## Differential formulation
(there is also an integral formulation of course)
$$\begin{align}
\nabla \times E &= - \frac{\partial B}{\partial t} \\
\nabla \cdot D &= \rho\\
\nabla \times B &= \mu \mu_0 \left( j + \frac{\partial D}{\partial t} \right)\\
\nabla \cdot B &=0
\end{align}$$
vector fields:
- $E$ is the electric field (strength) ("elektr. feldstärke"), measured in V/m or N/As
- $D$ is the electric induction / electric displacement field ("elektrische Flussdichte" / "dielektrische verschiebung" / "verschiebungsflussdichte"), measured in As/m^2
- $B$ is the magnetic flux density ("magnetische fluss dichte"), measured in T or Vs/m^2
- $H$ is the magnetic field strength, measure in A/m

constants:
- $\rho$ electric charge density
- $j$ electric current density
- $\mu$ magnetic field constant
- $\mu_0 = 4\pi 10^{-7} \frac{Vs}{Am}$ magnetic field constant in vacuum


## Some calculations and manipulations
If $\nabla \times E \neq 0$, $E$ is not conservative, and there is no scalar potential for $E$. But one can define a vector potential for $\nabla \times A :=B$ and write:
$$E = -\nabla \Phi_{el} - \frac{\partial A}{\partial t}$$
for a scalar function $\Phi_{el}$. There holds
$$D = \epsilon \epsilon_0 E = (1+\chi)\epsilon_0 E = \epsilon_0 E+ P$$
here, 
- $\epsilon_0 = 8.854 \cdot 10^{-12} \frac{F}{m}$ is the vacuum permittivity/electric constant ("elektr. Feldkonstante")
- $\epsilon$ is the (absolute) permittivity ("Permittivität" / "Dielektrizitätskonstante" / "dielektr. Leitfähigkeit") and measures the ability of a material to get polarized by an electric field
- $\chi$ electric susceptibility ("elektri. Suszeptibilität")

Relationship between $\mu_0$ and $\epsilon_0$:
$$\epsilon_0 = \frac{1}{\mu_0 c^2}$$
with $c$ being the vacuum speed of light. There holds
$$B = \mu_0 \mu H = \mu_0 (H+M) = \mu_0 (1+\chi)H$$

## Sources
Prof. Schütz - Grundlagen der Physik IIb

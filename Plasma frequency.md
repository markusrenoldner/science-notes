(frequency of electron oscillation in plasma)

Assume fixed ion grid, movable electrons, displaced by $\Delta x$ . Region 1 has positive, 2 has zero and 3 has negative charge.
![[MHD_ion-grid.png]]
What is the oscillation frequency of the electrons? Evaluate $E$-field. Take Gauss' law from [[Maxwell equations]]: $\nabla \cdot E = \frac{e n_0}{\epsilon_{0}}$ .  In one dimension: $\frac{dE}{dx}= \frac{e n_0}{\epsilon_{0}}$ , which gives
$$E=\frac{n_{0}e \Delta x}{\epsilon_{0}}$$
Equation of moten for electrons
$$m_{e}\frac{d^{2}\Delta x}{dt^{2}}= -eE = - \frac{n_{0}e^{2} }{\epsilon_{0}} \Delta x  $$
Which gives the oscillation frequency:
$$\omega_{pe} := \sqrt{\frac{n_{0} e^2}{\epsilon_{0}m_e}}$$
Therefore:
$$\omega_{pe} = \frac{\nu_{th}}{\lambda_{Dl}}$$
where $\nu_{th}=\sqrt{T_e/m_e}$ is the thermal velocity.



## Sources
- EPFL - Introduction to Plasma Physics, lecture 1c)
#paper 

by Antolin and Chanon

extension of "Analysis-aware defeaturing: problem setting and a posteriori estimatio" by Prof. Buffa, Chanon and Prof. Vazquez

## Abstract/main idea
Defeaturing (i.e. removal of small geometric artefacts/"features" of a computational domain) in order to reduce computational costs is analysed quantiatively.
This means, an a-posteriori error estimator between the defeatured and the orginal FEM problems (Poisson’s, linear elasticity, and Stokes’ equation) is being derived.

Morover, a refinment algorithm is described:
"Starting from a fully defeatured geometry, the algorithm determines at each iteration step which features need to be added to the geometrical model to reduce the defeaturing error. These important features are then added to the (partially) defeatured geometrical model at the next iteration, until the solution attains a prescribed accuracy."


## Content
2. define deafeaturing problem + notation
3. and 4. discuss poisson, lin elast and stokes problem
5. refinement strategy
6. validation using IGA/isogeometric analysis
appendix: proof ideas


## Notes

### notation
energy norm: $\vert\vert\vert \cdot \vert\vert\vert$

haussdorff meausure
?
https://de.wikipedia.org/wiki/Hausdorff-Ma%C3%9F
#todo 

simplified: tilde
defeatured: 0 subscript



Including complex geometrical features in the mesh might scale up the number of elements by factor 10.
This is not always necessary - but there is no quantitative measure for that yet.


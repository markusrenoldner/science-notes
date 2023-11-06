#paper 

by Antolin Pablo and Chanon Ondine

extension of "Analysis-aware defeaturing: problem setting and a posteriori estimatio" by Prof. Buffa, Chanon and Prof. Vazquez


## Abstract/main idea
Defeaturing (i.e. removal of small geometric artefacts/"features" of a computational domain) in order to reduce computational costs is analysed quantiatively.
This means, an a-posteriori error estimator between the defeatured and the orginal FEM problems (Poisson’s, linear elasticity, and Stokes’ equation) is being derived.

Moreover, a refinement algorithm is described:
"Starting from a fully defeatured geometry, the algorithm determines at each iteration step which features need to be added to the geometrical model to reduce the defeaturing error. These important features are then added to the (partially) defeatured geometrical model at the next iteration, until the solution attains a prescribed accuracy."


## Content
2. define deafeaturing problem + notation
3. and 4. discuss poisson, lin elast and stokes problem
5. refinement strategy
6. validation using IGA/isogeometric analysis
appendix: proof ideas


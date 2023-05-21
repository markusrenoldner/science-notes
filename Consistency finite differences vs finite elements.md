[[Finite Element Method (FEM)]]
[[Finite Difference Method (FDM)]]


Whether a discretisation is consistent (and the order of consistency) in the FDM setting is defined by the the truncation term, e.g.:

∂xx=1h2[1−21]+O(h2)∂��=1ℎ2[1−21]+�(ℎ2)

For instance we cannot construct a consistent (wrt the above definition) scheme for ΔΔ in 2D with a 44-stencil, and instead at least a 55-stencil is required. This is not the case for finite element methods, as it is perfectly fine to have P1�1 elements where some inner vertex has only 3 neighbours (corresponding to a 44-stencil, and one can indeed perform the Taylor expansion to verify that the scheme is not consistent wrt the definition for FDM). Instead bounds on the error can be derived per element (e.g. Larson-Bengzon) and in general guaranteeing consistency (for an appropriate mesh).

I am looking for references connecting the two, e.g. applying the FEM analysis to some "inconsistent" FDM stencils, that nevertheless lead to convergence (e.g. are consistent w.r.t. the FEM formulation)?



I think this question may lead to a lot of confusion, as there are different notions of consistency for FDM and FEM. For instance when one thinks of FEM consistency, it is often Galerkin orthogonality. What do you mean by FEM analysis on a FDM? 


Yes, I realized the question is probably not very good after thinking for a while about it. After all in FDM we do not define basis functions, and thus consistency in terms of orthogonality is probably a stretch there. Nevertheless I am interested if there are any references discussing this in more details and comparing FEM, FDM, and potentially FVM.


## Source
https://math.stackexchange.com/questions/4325853/consistency-finite-differences-vs-finite-elements
---
type: idea
title: >-
  Unified radial envelope bound for one-sided and two-sided Gaussian multifactor
  BH
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags: []
---

Candidate strengthening of idea_ad11695134a0. For two-sided tests set p(x)=2barPhi(x), u=p^{-1}(q), b=chi_d upper-q quantile (b>=u), Delta2=log[q/p(b)]. The conditional boundary-null tail f_t(y)=P(|r y+sqrt(1-r²)epsilon|>=p^{-1}(t)) is even and nondecreasing in |y|, has marginal integral t, hence f_t(y)p(|y|)<=E[f_t(Y)1(|Y|>=|y|)]<=t. Both outer-strip envelope integrals are therefore <=Delta2. Source central envelope bound is <=1/2+gamma_r*u/sqrt(2pi) for the source q range; r=1 central0, fullouterDelta2. Thus proposed FDR^(2)<=q+q*pi0*(1/2+Delta2)+(q*u/sqrt(2pi))*m^{-1}sum gamma_i. Same formula holds one-sided with u=barPhi^-1(q), Delta1=log[q/barPhi(b)], composite null <=0. Under d loglog(1/q)=o(sqrt(log(1/q))), both Delta=o(sqrt L). One-sided gamma<=1 yields sharp1/sqrtpi. Two-sided only yields1/sqrtpi generically, but achieves target upper constant1/(2sqrtpi) if limsup m^{-1}sum gamma_i<=1/2, e.g. all null norms>=3/5. This restricted two-sided upper bound does not establish sharpness or full unrestricted conjecture. No claim approved; needs separate frozen asset, countersearch, complete proof, independent verification, literature assessment.

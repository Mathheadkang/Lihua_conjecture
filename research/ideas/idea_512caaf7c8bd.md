---
type: idea
title: A signed gradient bound gives a direct feasible-cutoff path
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - proof-simplification
  - all-D-budget
  - direct-contact-comparison
---

New analytic simplification of the population candidate's global first-contact proof. NOT a new statement or an unrestricted result. In the regular-angular candidate let A=K/kappa, c=2A Md, B=-F_x, D=r F_r. The component negative-part bound I_minus<=cF holds for ALLD, not onlyD<=0. The low-mean split satisfies B_low<=I_plus/ell, I_plus=D+I_minus; the complementary bound is B_high<=2A*g_r(0)/H_r(ell)*F. Thus the stronger signed inequality B<=D/ell+L F holds for everyD, with L=A[2Md/ell+2g_r(0)/H_r(ell)]. This applies both tooneSallrealmeans andfoldedtwoSusingtheir correct splits from idea_e189af0f66e7.

Setell=r/(2sqrt d), r>=r0=max(u,52A sqrt d/u), r<=Lrad=sqrt d+2u, u>=104A. ThenL<=u/2. ChooseEXACTpath X'=4A Md/(rX), X(r1)=x1>=u. Let beta=(r/ell)X'=8A Md sqrt d/(rX)<=2Md/13<1. WhereverF(r,X)>0, the calibrated logratio J=log(qF(r,X)/(sQ(X))) obeys
J'=D/(rF)+(h(X)-B/F)X' >= [D/(rF)](1-beta)+(h(X)-L)X' >= -c(1-beta)/r+(X/2)(2c/(rX)) = c beta/r>0.
Here D/F>=-c, h>X andL<=u/2<=X/2. Hence a positive startingF cannot vanish alongthisfinitepath: increasingJ andpositivefiniteQ(X) ruleoutafirstzero bycontinuity. ANYinitialfeasiblecontacttherefore staysfeasible alongX, directly yieldingxfirst(r2)^2<=xfirst(r1)^2+8A Md log(r2/r1). No moving maximum, epsilonbarrier, regular-rootdifferentiation or root-switchcaseanalysis is required. Clipandusethepartitiontransport asbefore. WithA1 thissimplifiesthecurrentisotropicgoalproof. Atcontactfx0 the same signedinequalityalso givesD>=ell(h-L)F>0, strengthening the REG/Sardinterface.

Root derived this exact positive-part calculation; independent audit is pending before nativeadoption. Important: L here is the local gradient coefficient, not the upperradiuscutoff Lrad; finalproofshoulduse distinctnotation. Allconditionsandthefixedpopulationkernelremainessential. This doesnotcontrolatomicfinitearrayswithoutthepopulationlimitassumptions.

---
type: idea
title: A unique diffuse fold with a nearby higher competing well
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_diffuse_fold_deformation_recovery
tags: []
tried_in:
  - target: gaussian_bh_diffuse_fold_deformation_recovery
    round: 3
    slot: 1
    statement_digest: c94a3fdf2ffe058f0be84badf476c4d08154e9cac43cf7bcae563b030a494568
    outcome: >-
      cand_gaussian_bh_diffuse_fold_deformation_recovery_r3_s1_higher_well_fixed_gap
      failed: H1 ✓ H2 ✓ H3 ✓ H4 ✓ H5 ✓ H6 ✓ NOT ✗ — NOT fails: the fixed higher
      local well and all globally largest-root switches preserve the asserted
      signed variations, sublinear cost, ordinary finite recovery, and remaining
      conclusion clauses for both deformation signs.
---

New nonlinear competing-root object, distinct from the tested convex linear-quantile family and from an inadmissible equal-depth double well. Actual perturbed FDR/finite recovery not yet checked. Fix q=1/4,p=1/2,sigma=1/2,H=R,v0=+1,v1=-1,rho=-1/2. Let r(c)=p+(1-p)c, u(r)=S^{-1}(qr), and set g(c)=-1+(1/100)(c-1/4)^2[(c-3/4)^2+1/100], vartheta(c)=u(r(c))-g(c). Then vartheta is C³, strictly decreasing and positive on[0,1]: u>0, 1 minus the small polynomial is positive, |g'|<.02 while |d/dc u(r(c))|>=q(1-p)sqrt(2pi)>.25. The global minimum is unique at c*=1/4,b=-1,r*=5/8; g''(c*)=13/2500>0. There is an additional local maximum c_-=(25-sqrt(17))/40 and a higher local minimum c_+=(25+sqrt(17))/40 near .728. Its positive height gap is small (about2.4e-5) but fixed. Thus g is not globally convex and genuinely has a competing higher-rank well. Test both signed bumps with a sufficiently large admissible K and epsilon small relative to the fixed well gap and support separation. Determine actual largest ranks globally, not just the first local minimum: for finite exploratory epsilon the higher well can switch on, whereas the theorem only concerns a sufficiently small-epsilon regime of one fixed model. Check the exact birth shift, cost, full-FDR derivative and finite canonical recovery before any NOT verdict. Coupling the well gap to epsilon would change the model and cannot refute the stated quantifiers.

## Tried

- Search round 3 for gaussian_bh_diffuse_fold_deformation_recovery (slot 1): cand_gaussian_bh_diffuse_fold_deformation_recovery_r3_s1_higher_well_fixed_gap failed: H1 ✓ H2 ✓ H3 ✓ H4 ✓ H5 ✓ H6 ✓ NOT ✗ — NOT fails: the fixed higher local well and all globally largest-root switches preserve the asserted signed variations, sublinear cost, ordinary finite recovery, and remaining conclusion clauses for both deformation signs.

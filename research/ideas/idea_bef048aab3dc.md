---
type: idea
title: Non-atomic circular null directions approximated by regular polygons
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_common_loading_wasserstein_fdr_continuity
tags: []
tried_in:
  - target: gaussian_bh_common_loading_wasserstein_fdr_continuity
    round: 3
    slot: 2
    statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
    outcome: >-
      cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r3_s2_circular_polygon
      failed: H1 ✓ H2 ✓ H3 ✓ H4 ✓ H5 ✓ H6 ✓ NOT ✗ — NOT fails: the circular
      population and canonical regular polygons satisfy all checked conclusion
      clauses, their actual largest ranks converge almost surely outside
      Gaussian-null conditional critical levels, and their full FDRs converge.
---

Distinct next concrete falsification object; all conclusion clauses and microscopic inequality remain to be independently checked before a NOT verdict. Fix q=1/4, sigma=1/2, H=R². Let pi put theta=0, ell=1 and v uniform on the unit circle. Let pi_n be equal mass on the n regular-polygon directions with the same theta,label. Under nearest-angle coupling W1(pi_n,pi)<=pi/n. Write residual field X(v)=G dot v, G standard bivariate Gaussian, R=||G||, s=sqrt(3)/2 and independent common Z. Conditional on G and Z, scores are sR cos(angle)+sigma Z. The circular projection quantile suggests the exact population rejection event sigma Z >= C(R), C(R)=inf_{0<r<=1}{S^{-1}(qr)-sR cos(pi r)}. Since all labels are true, FDR should be E_R S(C(R)/sigma). For pi_n the exact ordinary n-test rejection event has critical value C_n(G)=min_{1<=k<=n}{S^{-1}(qk/n)-s a_(k)(G)}, with a_(k) the kth largest of G dot v_j. Coercivity as r down to zero at each finite R and circular quantile approximation suggest C_n(G)->C(R), hence FDR convergence after integrating Z. Check actual largest rank (not only nonempty rejection), root measurability, endpoint r=1, finite canonical approximation and the microscopic inequality for every a; do not turn this sketch into a failed-NOT candidate until those checks are complete. Unlike preceding nonatomic examples, this law has genuinely nonatomic directions rather than a continuum only of means. Finite covariance has rank at most3 and remains lawful.

## Tried

- Search round 3 for gaussian_bh_common_loading_wasserstein_fdr_continuity (slot 2): cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r3_s2_circular_polygon failed: H1 ✓ H2 ✓ H3 ✓ H4 ✓ H5 ✓ H6 ✓ NOT ✗ — NOT fails: the circular population and canonical regular polygons satisfy all checked conclusion clauses, their actual largest ranks converge almost surely outside Gaussian-null conditional critical levels, and their full FDRs converge.

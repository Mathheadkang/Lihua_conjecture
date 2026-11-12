---
type: idea
title: >-
  Repair covariance interpolation by fixing the alternative block and its SDP
  completion geometry
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags:
  - repair-after-countercertificate
  - global-fdp
  - fixed-alternative-block
---

Executable repair to test after failed plan plan_gaussian_bh_one_sided_global_corner_budget_20261104. Its unrestricted diagonal-majorant certificate (C) is false: a pure weak equicorrelation block among alternatives, with independent conservative nulls, gives unweighted dual cost growing like log N even though actual FDR<=q*pi0. The original covariance-specific scalar goal remains open. Do not reuse (C).

Partition indices into actual true nulls 0 and alternatives 1. Set B=diag(I_0,Sigma_11) and S_t=(1-t)B+t Sigma. This is a convex combination of unit-diagonal PSD matrices; for PD Sigma, B is PD, and singular models can be reached by the prior fixed-model regularization. At t=0 nulls are independent of one another and all alternatives, whose ORIGINAL joint covariance is retained, so superuniform-null leave-one-out gives FDR(B)<=q*pi0. The derivative Sigma-B has only null-null off-diagonal and null-alternative entries; all alternative-alternative derivatives are exactly zero. The previously established mixed-corner formulas still apply to this new affine path.

Define K from the integrated corner kernels on S_t for pairs with at least one null, set its alternative/alternative block and diagonal to zero. Then the exact gain is tr(Sigma K). A candidate stronger-but-testable certificate now keeps the actual alternative geometry: seek null diagonal D0 and symmetric alternative-block H such that M=embed_0(D0)+embed_1(H) satisfies M-K PSD and tr(D0)+tr(H Sigma_11)<=phi(u_q)/sqrt(2pi)+o(q*u_q) (or any bound with the same leading constant). For every PSD completion Gamma with null diagonal1 AND Gamma_11=Sigma_11, tr(Gamma K)<=that cost. This follows directly by pairing PSD matrices, not an assumed theorem. Unlike old (C), no arbitrary replacement of the alternative block is allowed. Sigma itself is a permitted completion. No claim this corrected certificate is true; test it and derive actual rank-gate/Schur-complement/Mehler estimates or give a counterexample. The pure-alt-block counterfamily has a constant new path and zero actual gain.

Keep heterogeneous negative null means at their actual grid boundaries. Do not impose uniform individual null budgets, covariance monotonicity, fixed-mean rank-one extremality, or a full-factor-envelope representation. Need uniform-in-dimension/means covariance bounds, singular limits and a genuinely proved analytic trace estimate; simply restating the scalar FDR target is not success.

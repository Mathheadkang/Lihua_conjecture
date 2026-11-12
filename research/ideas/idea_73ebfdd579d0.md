---
type: idea
title: >-
  A checkable analytic proof of the equicorrelation endpoint mismatch and the
  failure of sigma-uniform submodel compression
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_common_loading_uniform_submodel_compression
  - gaussian_bh_exchangeable_array_variational_compactification
tags: []
---

Analytic follow-up to idea_ed169268dd35 and its diagnostic-provenance correction idea_dc109abc47ba. This is a complete candidate argument for independent checking, not an approved counterexample and NOT a refutation of the active fixed-sigma statement. Use the source-verified fixed-rho formula in Dey2024, section4.2 Theorem4.3, https://doi.org/10.1007/s00362-024-01613-6 ; its import/approval is still a separate gate.

Fix q in (0,1/2), L=log(1/q), epsilon=sqrt(rho), tau=sqrt(1-rho). Put u_q(x)=S^{-1}(q S(x)) and d_q(x)=u_q(x)-x. For x>0, normal hazard bounds t<=h(t)<=t+1/t give
(u_q(x)^2-x^2)/2 <= L <= (u_q(x)^2-x^2)/2+log(u_q(x)/x).
Hence x d_q(x)->L as x->infinity. With y=epsilon x, the barrier is exactly [x d_q(x)]/y+y/(1+tau). For any delta in (0,L), choose X so L-delta<=x d_q(x)<=L+delta for x>=X. The infimum over x>=X is bounded below by 2sqrt((L-delta)/(1+tau)); evaluating at y=sqrt((L+delta)(1+tau)), feasible for small epsilon, bounds it above by 2sqrt((L+delta)/(1+tau)). The region x<=0 has numerator u_q(x)-tau x>=S^{-1}(q)>0. On [0,X], d_q has a strictly positive minimum. Thus these remaining barriers diverge as epsilon->0. Let epsilon->0 and delta->0: the GLOBAL infimum b_rho tends to sqrt(2L), so the N-first equicorrelated all-null FDR tends to L_q=S(sqrt(2L)), strictly below q. The diagonal limits differ from independence, whose finite BH FDR is exactly q. Every inequality, escape regime and use of the fixed-rho source theorem needs independent verification.

This yields a concrete parameter-family obstruction to a sigma-uniform or sigma=0 version of scalar compression. For each m choose rho_m->0 so the fixed-m equicorrelated FDR is within1/m of q (finite Gaussian covariance continuity) and S(b_rho_m) is within1/m of L_q. Then choose N_m arbitrarily large so the N_m full FDR is within1/m of S(b_rho_m) and m(m-1)/(2N_m)<=1/m. For iid index sampling, the no-collision submodel has exactly the m-dimensional equicorrelated law; collision changes the averaged FDR by at most its probability. Therefore averaged sampled FDR->q but full FDR->L_q, a nonzero gap. Jensen also prevents vanishing coupled-FDP error. These covariances have maximal feasible common loading tending to zero; they do not satisfy any one fixed positive-sigma class along the family.

No numerical value is used in this argument. The current positive-sigma theorem and pointwise supremum reduction W_sigma->F_1 remain compatible: do not replace finite-model/supremum VALUE comparisons by pointwise continuity of the infinite-array functional at sigma0. Conversely, private-noise smoothing at fixed positive sigma can still use the newly proposed array continuity; the endpoint obstruction concerns removing the common loading, not every regularizer.

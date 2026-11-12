---
type: idea
title: >-
  Exact first mixed small case: four two-sided tests with one shifted factor
  test
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - multifactor_radial_fdr_bounds
tags:
  - small_cases
  - exact_integration
---

Unresolved test family, not a counterexample: take m=4,d=1, two-sided testing, theta=(0,0,0,mu) with mu>0, a=(r_1,r_2,r_3,1), and 0<r_1<r_2<r_3<1. Then T_i=r_i Z+sqrt(1-r_i^2) epsilon_i for i<=3 and T_4=mu+Z; the true-null proportion is 3/4. This is the first mixed small case not excluded by the generic harmonic comparison: (3/4)H_4=25/16 exceeds 1+3/8=11/8. For d=1, Delta_2=0, so the proposed bound before the cap is q[11/8 + u_2(q)(gamma_1+gamma_2+gamma_3)/(4 sqrt(2 pi))]. Distinct null loadings avoid the extra rejection-count restriction forced by duplicated null p-values.

The exact FDR requires only one Gaussian integral, not a simulation sweep. Conditional on Z=z, null p-values are independent, and at t in (0,1), F_i,z(t)=Phi-bar((u(t)-r_i z)/sqrt(1-r_i^2))+Phi-bar((u(t)+r_i z)/sqrt(1-r_i^2)), where u(t)=Phi-bar^{-1}(t/2). Partition each null p-value by the five bins with endpoints 0,q/4,q/2,3q/4,q,1. Their conditional bin probabilities are differences of these CDFs; the alternative p-value 2 Phi-bar(|mu+z|) fixes its own bin. For each of the 5^3 null-bin assignments, compute N_k=# {p_i<=qk/4}, R=max({0} union {k:N_k>=k}), and FDP=(R-1{p_4<=qR/4})/(R vee 1). Sum over assignments and integrate against phi(z)dz.

No parameter choice has been certified to violate the target. This family is recorded because the earlier generic obstruction leaves it open; no additional local computation was run.

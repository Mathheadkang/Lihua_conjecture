---
type: idea
title: >-
  Capped per-null conditional envelopes become vacuous even for independent
  Gaussian nulls
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
  - lei2026_conditional_fdp_bound
tags:
  - gaussian-bh
  - conditional-envelope
  - common-cutoff
  - dimension-uniform
  - proof-obstruction
---

This is an obstruction to a proof route, not a counterexample to either sharp FDR target. Take m independent standard Gaussian null statistics, represented by d=m, A=I_m and zero residual noise, and condition on the full Gaussian vector Z. The one-sided p-values U_i=barPhi(Z_i) are iid Uniform(0,1), and their conditional cdfs are F_{i,Z}(t)=1{U_i<=t}; degenerate conditional variables are conditionally independent, so the approved conditional leave-one-out bound applies. The two-sided iid standard Gaussian model gives exactly the same Uniform calculation.

For fixed q in (0,1), define S_i=sup_{0<t<=q} F_{i,Z}(t)/t=1{U_i<=q}/U_i. Then E S_i=infinity. For every K>=1/q, X_i=S_i wedge K satisfies E X_i=1+log(qK) and E X_i^2=2K-1/q. To prove the capped bound B_m(q)=E[min{1,(q/m)sum_i S_i}] tends to 1, choose any finite K with q[1+log(qK)]>1. The ordinary strong law for bounded iid X_i yields liminf_m (q/m)sum_i S_i>=q E X_i>1 almost surely; hence the cap tends to 1 almost surely, and bounded convergence gives B_m(q)->1.

The failure is uniform in q, not merely a fixed-level artifact. Set m(q)=ceil(exp(2/q)/q) and truncate at K=m(q). Then q E X_i=q[1+log(qm)]>=2+q and Var X_i<=2m. Chebyshev gives P{(q/m)sum_i S_i<1}<=2q^2/(1+q)^2, so B_{m(q)}(q)>=1-2q^2/(1+q)^2->1. Therefore the supremum over dimension of this capped conditional envelope is exactly 1 at every fixed q, and it cannot have a dimension-free O(q sqrt(log(1/q))) upper bound.

By contrast, with R_i the BH count after replacing U_i by zero, U_i is independent of R_i and 1<=R_i<=m. The exact identity 1{i rejected}/(R vee 1)=1{U_i<=q R_i/m}/R_i gives E[1{i rejected}/(R vee 1)]=q/m, and summing proves FDR=q. The independent model therefore illustrates precisely the lost coupling between the conditional cdf and the actual BH threshold. It is consistent with, and does not refute, the two unrestricted sharp upper-bound targets.

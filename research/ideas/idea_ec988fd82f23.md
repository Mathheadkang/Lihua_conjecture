---
type: idea
title: Small-size harmonic obstructions for the radial BH bound
status: draft
idea_kind: observation
origin: agent
related_assets:
  - multifactor_radial_fdr_bounds
tags:
  - small_cases
  - search_obstruction
---

No counterexample was found in the small_cases direction. For any dependence with superuniform true-null p-values, FDR <= q*pi_0*H_m, where H_m=sum_{k=1}^m 1/k. To verify without an independence assumption, partition a null p-value into ((k-1)q/m,kq/m]; a rejection in the kth interval has R>=k, so its FDP contribution is at most 1/k. Summation by parts and F_i(t)<=t give an expected contribution <=(q/m)H_m. Sum over the true nulls.

Both tracks: the displayed radial bound before the cap is at least q(1+pi_0/2). Since H_2=3/2 and pi_0<=1, q*pi_0*H_m <= q(1+pi_0/2) for m<=2. Thus no m<=2 instance, at any factor dimension or admissible means/loadings, can violate the target.

One-sided track: the chi_d upper-q quantile b is at least the chi_1 upper-q quantile, because ||Z||>=|Z_1|. Therefore Phi-bar(b)<=q/2 and Delta_1>=log(2). The target bound before the cap is at least q[1+pi_0(1/2+log(2))]. Since H_4=25/12 < 3/2+log(2), q*pi_0*H_m is below this target for every m<=4. This excludes every one-sided m<=4 case, including negative true-null means and singular loadings.

For two-sided m=3, mixed cases have pi_0<=2/3 and are also excluded by the harmonic bound; only the all-null case can evade that generic comparison. For two-sided m=4, cases with at most two true nulls are excluded; the first mixed case not excluded by this argument has exactly three true nulls. These are obstructions to small counterexamples, not a proof of the target for arbitrary m.

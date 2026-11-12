---
type: idea
title: Four-test shifted-factor family excluded by a null-Simes FDP envelope
status: draft
idea_kind: observation
origin: agent
related_assets:
  - multifactor_radial_fdr_bounds
tags:
  - counterexample-search
  - small_cases
  - two-sided
---

Round 2, slot 1: the entire test family in idea_bf23916c98ed is excluded analytically, without quadrature. For m=4,d=1, theta=(0,0,0,mu), mu>0, and 0<r1<r2<r3<1, the three null absolute statistics are conditionally independent given W=|Z|. Their folded-normal conditional densities have monotone likelihood ratios in W: for x'>x, the posterior W density ratio is proportional to cosh(c*x'*W)/cosh(c*x*W), increasing in W. Their null p-values consequently have positive regression dependence. A self-contained leave-one-out telescoping calculation gives the superuniform three-null Simes statistic S=min_j 3*P_(j),0/j.

For four-test BH, if the alternative is not rejected and V>0 then S<=3q/4 and FDP=1. If it is rejected with v=1,2,3 nulls, then S<=3q(v+1)/(4v) and FDP=v/(v+1). Hence FDP <= (1/4)1{S<=3q/4}+(1/12)1{S<=q}+(1/6)1{S<=9q/8}+(1/2)1{S<=3q/2}. Superuniformity yields FDR<=(29/24)q. All four thresholds are below one in the permitted two-sided range. The target bound in this family is >=(11/8)q, so the gap is at least q/6.

The full self-contained calculation and hypothesis checks are in the NEW failed candidate research/candidates/cand_multifactor_radial_fdr_bounds_r2_s1_four_test_mixed_prds.md. This observation is a family-specific search obstruction, not a proof or certification of the general multifactor target. It does not impose any additional assumptions on the alternative p-value.

---
type: idea
title: Correlated three-group mixed-label numerical probe for rare Mills clones
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_rare_clone_mills_variation
tags:
  - rare-clones
  - small-cases
  - numerical-evidence
  - three-groups
tried_in:
  - target: gaussian_bh_rare_clone_mills_variation
    round: 4
    slot: 1
    statement_digest: c7939c23ae577add03c56534f1a6ec07179140d4317ffdd0a9a1aaf699a67fea
    outcome: >-
      cand_gaussian_bh_rare_clone_mills_variation_r4_s1_correlated_three_group_settled
      failed: H1 ✓ H2 ✓ H3 ✓ H4 ✓ H5 ✓ H6 ✓ H7 ✓ NOT ✗ — NOT fails: the exact
      fixed correlated three-group mixed-label object has the actual
      finite-copy/common-largest-crossing limit, all normalization/label/cost
      conclusions, and the asserted signed inverse-Mills variation with an
      $O(\varepsilon^2)$ expectation remainder.
---

## Concrete object

Fix N=3, q=0.2, selected coordinate i=1, means theta=(0,0.8,-0.5), and G standard Gaussian in R^3. Take direction rows v1=(1,0,0), v2=(0.6,0.8,0), v3=(-0.4,0,sqrt(0.84)). Thus Sigma=[[1,0.6,-0.4],[0.6,1,-0.24],[-0.4,-0.24,1]], with determinant 0.5376>0. Original labels are (1,0,1). This differs from the earlier independent two-group tests: it has two opposite-signed correlations with the selected zero-null coordinate and three possible rank faces.

## What was checked numerically

Use exactly the target offset law and the common global population crossing. U=0.8416212335729139; (u1,u2,u3)=(1.5010859460440247,1.1107716166367856,0.8416212335729139); L=1.9896897067216244. Conditional on T1=t, the backgrounds have independent residuals, means 0.8+0.6t and -0.5-0.4t, and standard deviations 0.8 and sqrt(0.84).

For each k=0,1,2, numerically find the largest clone-compatible rank xk in [k,k+1]. Writing r=k+1 and z(v)=(N/q)(phi(v)/v-S(v)), the partial-group branch is xk=r-epsilon*z(v), with t=u(xk)+epsilon*(1/U-1/v). The activation minimizer solves v=u(r-epsilon*z(v)); the larger-v root is used. Outside the strip [ur,ur+epsilon/U], xk is its ordinary integer value. Route globally: rank x2 if both backgrounds exceed u(x2); otherwise rank x1 if at least one exceeds u(x1); otherwise rank x0, including zero.

Let pA,s and pB,s be the conditional background exceedance probabilities at u(xs), s=1,2. Then P2=pA,2*pB,2, P1A=pA,1*(1-pB,2), P1B=pB,1*(1-pA,2), and P0=1-P2-P1A-P1B. The numerical conditional population FDP used is P2*(x2-1)/x2 + P1A*(x1-1)/x1 + P1B + P0*1{x0>0}. This retains fractional denominators and the common largest-rank routing.

The conditional ordinary-BH face calculations give mu approximately (0.029458325400516544,0.07084889794080816,0.0029130228135272993). The asserted signed derivative is therefore approximately -0.061494242008718454. Integrating the population-minus-original conditional FDP over all three strips, with each activation jump split explicitly and Simpson quadrature with 1600 panels per smooth piece, gives slopes:

- epsilon=0.02: -0.06111835131880446;
- epsilon=0.01: -0.06130648707100713;
- epsilon=0.005: -0.061400414035061836;
- epsilon=0.002: -0.06145672294142297;
- epsilon=0.001: -0.061475484512214504.

These are numerical agreement evidence only; the slope discrepancy appears proportional to epsilon. They neither refute nor prove the target.

## Remaining checks

Independently verify the finite-K-to-population limit, the global three-branch reduction, rigorous integration/root and remainder bounds, and the resulting derivative in this exact fixed object. The numerical roots and quadrature were not certified by interval bounds. All target conclusions, including finite-copy quantile effects and measure-cost claims, have not been independently certified for this object. No NOT verdict was established and no candidate file was created.

## Tried

- Search round 4 for gaussian_bh_rare_clone_mills_variation (slot 1): cand_gaussian_bh_rare_clone_mills_variation_r4_s1_correlated_three_group_settled failed: H1 ✓ H2 ✓ H3 ✓ H4 ✓ H5 ✓ H6 ✓ H7 ✓ NOT ✗ — NOT fails: the exact fixed correlated three-group mixed-label object has the actual finite-copy/common-largest-crossing limit, all normalization/label/cost conclusions, and the asserted signed inverse-Mills variation with an $O(\varepsilon^2)$ expectation remainder.

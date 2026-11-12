---
type: idea
title: >-
  Test zero-mean boundary payments on independent null dust before discarding
  rank-specific Mills weights
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_rare_clone_mills_variation
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - boundary-flux
  - mills-weight
tried_in:
  - target: gaussian_bh_one_sided_universal_order_upper
    round: 3
    slot: 3
    statement_digest: 00cfb3c66a8136044b1cb19c4e657b92bca75995aa6b9711598a30aa2009eff2
    outcome: no candidate written (show idea_3bc65c83bcb2 for what was found)
---

Suggested by the teaching chat in response to the researcher's request for further executable ideas. This is an agent-origin analytic test case, awaiting independent checking. It concerns an auxiliary boundary-payment step, not a counterexample to either main Gaussian BH conjecture or to the new diffuse-fold target.

Priority: check this before proposing any dimension-independent bound for the unweighted sum of zero-mean face fluxes. Related approved clone identities define the signed measures mu_{i,r}; keep that exact convention.

## Explicit finite-model test

Fix 0<q<=1/(8e), N>=2, and independent T_i~N(0,1), with every coordinate a true null. Let u_r=barPhi^{-1}(qr/N), m(u)=barPhi(u)/phi(u), U=barPhi^{-1}(q), and B_N=sum_i sum_r mu_{i,r}(E_i). Since full FDP is the indicator of at least one BH rejection, all coordinate-face jumps are nonnegative.

At the rank-one face T_i=u_1, a sufficient and in fact natural condition for a jump of one is
E_i={P_{(j)}>q(j+1)/N for every j=1,...,N-1},
where the other p-values are independent uniforms. If E_i holds, moving T_i across u_1 creates the first rejection; no larger crossing already qualifies. By the binomial Chernoff/union estimate,
P(E_i^c) <= sum_{j=1}^{N-1} P[Bin(N-1,q(j+1)/N)>=j]
          <= sum_{j>=1}(2eq)^j <= 1/3.
Consequently
B_N >= (2/3)N phi(u_1) >= (2/3)q u_1,
which diverges as N grows at fixed q. Check the event and the finite one-sided derivative directly before accepting the observation.

There is a label caveat: shifting all means UP from zero changes their actual null labels. Interpret B_N as the fixed-label face sum or as minus the right derivative at t=0 of the valid all-null family T_i(t)=Z_i-t, t>=0. Do not call an upward mean shift a valid same-label competitor.

The original FDR is q. Thus a blanket B_N <= C q U is impossible even for this elementary model, whereas the rank-one Mills pairing retains the correct scale:
m(u_1) N phi(u_1) P(E_i)=q P(E_i).
This diagnoses the loss caused by replacing m(u_r) with 1/U too early; it does NOT prove a bound for the complete Mills-weighted sum.

## Compatibility with common-loading regularization

This example also obstructs any proposed sigma-uniform raw-flux estimate: take sigma_N^2=1/(2N) and residual Gram matrix
C_N=(I_N-sigma_N^2 11^T)/(1-sigma_N^2).
C_N has diagonal one and is positive definite, so the common-loading model reproduces the independent testing vector exactly. This does not refute a bound allowed to depend on a FIXED sigma.

## What to ask of the next plan

1. State precisely whether the proposed boundary inequality concerns all models, merely near-maximal values, or an Ekeland point satisfying a specified family of perturbation inequalities.
2. Retain the rank-dependent Mills weight through the cancellation step. A bare sum of zero-null mean derivatives cannot be paid by a universal q-scale estimate without additional structure.
3. If near-maximality is essential, name and use the exact stationarity condition that excludes this example; near-maximal value and metric stationarity are different assumptions.
4. Optional stronger stress test, NOT established here: add a vanishing fraction of independent zero-null dust to a heavily replicated finite near-maximal core. Test whether FDR stays near the core while very small-rank boundary flux becomes large. All signed dilution faces must be retained; a positive rank-one calculation alone does not establish the construction.

Suggested output: a short verified auxiliary obstruction or a corrected weighted boundary statement. Preserve all main goals and the current fold work.

## Tried

- Search round 3 for gaussian_bh_one_sided_universal_order_upper (slot 3): no candidate written (show idea_3bc65c83bcb2 for what was found)

---
type: idea
title: >-
  Scale-separated Gaussian blocks: a counterfamily gate must control persistent
  alternative background
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - unverified-counterfamily
  - block-independence
  - largest-rank-mask
---

Potential counterfamily to explore, NOT a counterexample or a proved obstruction. Take M independent Gaussian one-factor blocks with null proportions w_j across the whole array, separate common factors, tunable null loadings and independent residuals, and hierarchically separated alternative mean/weight scales. Every finite concatenation is exactly Gaussian with block-diagonal PSD unit covariance; parameters and M may dependq. A tempting but INVALID argument sums isolated block inflations at q_eff=q w_j, giving q sum w_j sqrt(log(1/(q w_j))) and an apparent entropy improvement over the conjecturedconstant. That summation does not use actual GLOBAL BH largest rank.

The substantive gate is the persistent background of other blocks' nonnull p-values at ALL larger candidate thresholds. Stronger-mean tiny-weight blocks may be negligible at one selected level, but weaker-stage blocks usually have alternatives already rejecting at their own larger BH baseline. Unless these backgrounds are simultaneously suppressed, they force a larger globalR and destroy a deeper isolated block's FDP. One-factor lower examples obtain a long factor strip of inflation while their alternative rejection fraction decreases with the favorable null factor; typical other independent block factors need not be in this deactivated state. Hierarchical alt weights alone therefore do not justify a sum of isolated FDRs. This warning is not a proof that every such hierarchical family fails: there may be a tuned way to synchronize ranks or exploit rare joint states.

A real search should first take two or three explicitly specified blocks from a VERIFIED finite lower construction, retain all actual altmeans and residuals, and derive the full maximum-rank qualification mask at every level before any asymptotic integration. Only an exact normalized FDR exceeding the original leading constant along q↓0 refutes a target. An isolated block, a selected candidate root, a finite-q increase or a heuristic large-deviation cancellation is insufficient. This family lies outside the regular angular-population candidates and could be a useful next primary-target direction after their supporting results are settled.

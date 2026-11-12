---
type: idea
title: >-
  Paused checkpoint: chronological signed-jump matching cancels resets but
  leaves continuous-recovery charge
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_finite_signed_p_path_identity
  - cx_gaussian_bh_positive_p_path_jump_budget_r4_s3_tangent_reserve_reset
tags:
  - pause-checkpoint
  - chronological-pairing
  - draft-diagnostic
---

Checkpoint of the completed PLAN-worker derivation at the researcher's explicit pause-before-Sync request. This is a draft observation, not independently verified and not a main proof. The worker was interrupted; no additional proof development is authorized before Sync completes.
Use the approved finite signed conditional p-path notation A_i and nondecreasing g_i. For almost every height y, pair a downward crossing at a merged jump e with the next upward crossing of that same height. This next crossing can be a merged upward jump or continuous recovery; initial upward crossings are recorded separately. Keep all original null labels and every alternative response. Define K_i by summing g_i(e) times the height mass of downward jumps whose next upward crossing is continuous. Put H_i=integral_(0,q) g_i(t) A_i'(t) dt. The derived finite levelwise decomposition is H_i-K_i = initial-continuous-crossing weight + sum_(down-to-continuous pairs) integral [g_i(recovery)-g_i(e)] dy. Every summand is nonnegative. Comparing with all initial crossings and all jump/continuous pairs gives 0<=H_i-K_i<=b_i<=1, where b_i is the approved baseline g_i(q)-integral A_i dg_i. Hence q/N sum_i E K_i <= FDR <= q*pi0 + q/N sum_i E K_i. With zero null means g_i=1, H_i-K_i is precisely the initial continuous height mass in [0,1]. This exposes saturation: the remaining continuous-recovery charge is the unknown FDR up to an additive O(q), not an independently paid estimate.
In the approved reserve-reset example, the selected identical-null block has physical mass alpha N. Its selected rank is at least alpha N; on affine pieces A_i'<=min{1/(q alpha),1/t}. Therefore H_i<=1+log(1/alpha) for every residual value, uniformly in N, so the diverging unsigned jump variation in that block cancels under this pairing. This does not control all original null labels or prove the main rate. Compatible Hall-cut circulation is not assumed to be a global potential.
No pending main proof plan or target edit has been produced. The first unpaid task is an independent Gaussian-averaged bound on the explicit continuous-recovery charge, preserving original same-rank masks. The separate critical-scale null-cohort approach remains an untested draft idea. Resume only after the requested Sync completes.

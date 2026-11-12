---
type: idea
title: >-
  Pre-Gaussian determinantal sampling as a test of adaptive frame selection
  costs
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

Unproved reserve for the unrestricted order bound, after the conditional-envelope obstruction. Test a deterministic determinantal mixture before committing to a long proof. Let v_i be original unit true-null Gram vectors, M=N^{-1} sum_{i in I0} v_i v_i^T, and L_lambda=(lambda/N)(v_i.v_j)_{i,j in I0}. A finite L-ensemble samples S before the Gaussian innovation with probability det((L_lambda)_S)/det(I+L_lambda). For any realized selected-null set A, finite determinant expansion gives P(S subset A)=det(I+(lambda/N) sum_{i in A}v_i v_i^T)/det(I+lambda M). This elementary identity must be derived rather than cited.

The proposed mechanism is to average high-null intersections using this pre-Gaussian sampling, which favors independent directions, rather than choose an adaptive fractional frame or pay for every subset. Rank-one clone collapse and independent directions are mandatory initial tests. Main open gates: relate the determinant ratio (including the empty subset) to the original FDP V/R without substituting another selector; derive an intersection/surface estimate under the determinant weights with all hypotheses of the approved frame kernel checked; and choose or integrate lambda without a log N, rank, private-noise or entropy loss. A determinant identity alone does not pay the Gaussian probability or prove the theorem. If the required rankwise comparison already fails for iid nulls or clones, record the precise failure and do not write a filler proof plan. No new completion root is proposed; nothing from this idea may be assumed as a theorem.

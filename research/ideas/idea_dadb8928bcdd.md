---
type: idea
title: >-
  Independent-block amplification does not preserve a fixed positive common
  Gaussian loading
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_simes_one_sided_uniform_linear_bound
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_common_loading_wasserstein_fdr_continuity
tags: []
---

The valid all-null independent-block amplification in idea_8699fa13f1f6 applies to the unrestricted Gaussian model class. It cannot be combined directly with the fixed-sigma common-loading q-log bound proposed in idea_4de18419c49d to prove the all-null Cq conjecture. A fixed common-loading representation of covariance Sigma requires Sigma-sigma^2 11^T >=0. Even B independent standard Gaussian coordinates have covariance I_B, for which I_B-sigma^2 11^T is PSD only when B sigma^2<=1. Thus independent block replication leaves the fixed-positive-sigma class once B grows. Removing common loading by finite-model covariance continuity gives only a pointwise sigma->0 supremum reduction and does not make a C_sigma bound uniform. Any proposed shortcut must explicitly control this loss; no existing theorem is refuted by this observation.

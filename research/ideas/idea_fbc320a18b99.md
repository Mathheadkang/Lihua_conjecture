---
type: idea
title: >-
  Padding yields monotonicity of the unrestricted one-sided worst-case FDR
  envelope
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

Candidate elementary reduction, not yet independently verified or adopted as a theorem. Let W(q) be the supremum of original one-sided Gaussian BH FDR over all finite N, all lawful means and PSD unit diagonal covariances. For 0<q<q'<1, fix any original N-test model. Uniformly K-copy every coordinate (exact-copy BH preserves FDP). Append M_K independent unit-variance Gaussian true-null coordinates with mean -A. At level q', on the event all dummy p-values exceed q', dummy tests never reject and the original copied model is run at effective level q_eff=q' K N/(K N+M_K). Choose integers M_K>=0 so q_eff tends to q. For each fixed K,M_K let A tend to infinity: probability any dummy p<=q' tends to zero, hence bounded FDP convergence gives FDR(original at q_eff). For fixed original finite model its FDR is continuous in level because finitely many boundaries p_j=q r/N have probability zero even for singular Gaussian covariance with unit marginal variances. Thus W(q')>=FDR(original at q), and taking supremum proves W(q')>=W(q). This concerns the supremum over models, not monotonicity of FDR for a fixed mixed model. Padding model depends on q'; cannot interchange supremum and averaging to obtain a common near-maximizer over an interval. Two-sided negative-mean dummies are not conservative, so this construction is only one-sided. Possible use in comparing q-level envelopes, but no near-maximal variation transfer or main order bound follows yet.

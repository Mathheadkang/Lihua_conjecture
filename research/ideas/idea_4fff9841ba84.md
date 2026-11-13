---
type: idea
title: Crossing subset gives the Mills-penalized bound with slack 1/2
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_simes_mills_penalized_subset_reduction
tags: []
---

Proof step found in the refute search: take K the k coordinates with t_i >= u = Phibar^{-1}(qk/N). Then int_{z_K}^u h = log(1/(Aq)) = L >= 1 exactly. With tau=h(z_K), d=u-z_K: tau(X_K - tau) >= tau d - h'(z_K) > tau d - 1, and L <= tau d + d^2/2 (since h' < 1), tau >= sqrt(2/pi), give tau d >= sqrt(L)/2 once L >= 0.39. Numerically the worst margin is about 0.5 (L=1, z_K large).

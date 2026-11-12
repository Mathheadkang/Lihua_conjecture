---
type: idea
title: >-
  Near-coincident marks retain unbounded recovery information; BH cancellation
  remains essential
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_mixed_coherence_trace_budget
tags: []
---

Independent planning audit after five refutation rounds found no executable proof of the unrestricted mixed trace budget. A generic covariance-only Gaussian-channel replacement of the finite-label entropy is insufficient: take k equiprobable marks c_j=sqrt(1-r^2)e_0+r e_j (j=1,...,k). Their trace covariance is at most r^2, but squared reconstruction error <r^2/4 implies nearest-neighbor label error bounded away from 1, hence the elementary Fano entropy inequality requires information of order log k. Isotropic channel noise can keep information cost O(r^2/sigma^2), but it does not also give dimension-free accurate mark recovery; resolving the residual directions brings rank dependence back. This diagnostic is about generic marks, not actual BH terminal laws, and is NOT a counterexample to either the mixed budget or the original conjecture. A new proof must exploit the actual signed BH rank/null/Mills structure rather than replacing it by bounded-mark covariance alone. Related source: El Alaoui–Montanari arxiv2109.00709v2 Theorem1, https://arxiv.org/html/2109.00709v2.

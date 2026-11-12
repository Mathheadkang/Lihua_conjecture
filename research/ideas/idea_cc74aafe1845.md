---
type: idea
title: >-
  Focused primary-source check leaves the unrestricted order bound open in this
  pass
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
tags: []
---

FOCUSED/PARTIAL discovery. Scholar and Crossref REST were inaccessible; this is not an exhaustive claim. Original papers and official versioned records were checked via find-papers and verify-citations in primary-source mode; this was not a publication, retraction, or bibliography audit. (1) Weijie J. Su, The FDR-Linking Theorem, arXiv:1812.08965v1, submitted 2018-12-21: official https://arxiv.org/abs/1812.08965v1 and original PDF https://arxiv.org/pdf/1812.08965v1, Theorem 1 page 2 equation (1.1): FDR <= pi0 q + pi0 q integral from pi0 q to 1 of FDR0(x) x^-2 dx. Even FDR0(x)<=x gives q log(1/q), not the desired q sqrt(log(1/q)). Use the official submission date, not the spurious 2026 date in rendered HTML. (2) Xianyang Zhang, Exact Simes inequalities for two-sided Gaussian tests, arXiv:2611.02513v1, 2026-11-02: https://arxiv.org/abs/2611.02513v1 and https://arxiv.org/html/2611.02513v1, section 2 Theorem 2.1 equation (2.1): under the global null, fixed m, uniformly over covariance including singular covariance, Simes is exact for alpha<=a_m; the following paragraph gives a dimension-dependent cutoff, not a uniform-in-N result. (3) Deepra Ghosh and Sanat K. Sarkar, Further Results on Controlling the False Discovery Rate in Two-Sided Gaussian Mean Testing, arXiv:2608.21267v2, 2026-08-24: https://arxiv.org/abs/2608.21267v2 and https://arxiv.org/html/2608.21267v2, sections 2.2 and 3 Theorem 3.1 equation (6): ordinary BH has a covariance-specific conditional-variance upper bound with tau_i=1/(Sigma^-1)_ii>0, not a singular or covariance-uniform order result. Do not assume a uniform limit as tau tends to zero. This focused checked pass found no direct full-scope theorem or noncircular new certificate; it does not claim that no such literature exists. Candidate background only; none is a new approved dependency. Search queries included Gaussian BH arbitrary covariance FDR sqrt log, dimension-free, and Simes negative Gaussian.

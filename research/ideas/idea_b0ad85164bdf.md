---
type: idea
title: >-
  Source-scope guardrails for conditional PRDS and Gaussian global-null
  shortcuts
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_conditional_compound_calibration
tags: []
---

Primary-source scope check (11 November 2026), recorded as an unapproved literature risk, not a proof dependency. Barber and Samworth, arXiv:2507.21465v2, Section 2.3 Proposition 6, https://arxiv.org/html/2507.21465v2#S2.SS3, gives PRDS compound p-values with FDR at least (3/8) min(alpha H_m,1), even under the global null. Thus the newly approved conditional independent calibration cannot be extended to arbitrary conditional PRDS kernels merely by replacing independence with positive dependence. Individual conditional superuniformity is absent in that lemma. Any Gaussian-specific block extension must use additional structure and prove its bound.

A separate current source, Xianyang Zhang, arXiv:2611.02513v1 (2 November 2026), https://arxiv.org/abs/2611.02513v1, concerns two-sided global-null Simes validity at fixed dimension with a dimension-dependent small-level range, or restricted growing block/degree classes. Its abstract does not supply the unrestricted one-sided mixed-null FDR theorem or a common small-q range over all dimensions. Full proofs have not been imported or independently audited here. These are source-scope guardrails, not accepted mathematical prerequisites.

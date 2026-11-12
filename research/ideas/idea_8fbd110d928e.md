---
type: idea
title: >-
  Above-median Gaussian convex comparison: useful source with fixed-diagonal and
  BH-cell limitations
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

New primary-source check: Colin B. Fogarty, Gaussian comparison above the median, arxiv2607.06874v2 (2 Sep 2026), https://arxiv.org/html/2607.06874v2 . Read Theorem2.1, Corollaries2.2-2.3 and proofs§3.1-3.3. Independent symmetric convolution cannot increase a closed convex set's probability when its convolved probability is at least one half; the Gaussian covariance corollary assumes Loewner ordering and applies also to singular covariances. Proof uses concavity of the Gaussian quantile of translated convex-set probabilities and pairing opposite shifts. Potential relevance is signed paired shifts in an extremal-covariance argument. Immediate applicability failures: two unit-diagonal covariance matrices cannot be nontrivially Loewner-ordered (PSD difference with zero diagonal is zero); individual actual BH cells generally have probability below one half; unions of cells and FDP superlevel sets need not be convex. Any use must provide a new convex high-probability representation or compensated-variance comparison; the theorem alone supplies neither the missing BH rank/Mills pairing nor the unrestricted order bound. Source is external and not an approved dependency.

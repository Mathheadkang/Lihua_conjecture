---
type: idea
title: >-
  Test antipodal rank pairing under a covariance-preserving two-copy Gaussian
  rotation
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags:
  - unproved_probe
  - global_rank_pairing
  - gaussian_rotation
---

Unproved global mechanism to test, not a new theorem. Let X,X' be independent centered Gaussian vectors with the actual covariance Sigma, and set T(theta)=mu+cos(theta)X+sin(theta)X'. Every theta has the original admissible law, including singular Sigma. Conditional on the two copies each coordinate is a sinusoid plus its mean, and antipodal theta+pi reverses the centered fluctuation while preserving mu. Centered true nulls have identical absolute statistics at the antipodal pair, while the same alternatives must supply both BH ranks. This may permit a finite-circle rank/arc charge that pools nulls globally and uses the two ranks together, rather than allocating a uniform sharp budget to each null. Candidate tools: exact largest-rank cell decomposition on the circle, finite coarea/rank-jump accounting, then averaging the two Gaussian copies (each null sinusoid amplitude has a Rayleigh marginal). First gate must be a concrete deterministic paired-rank identity or inequality, checked on N=2/3 and on the single-null staircase; it cannot simply be an expectation restatement of the target. Essential limitations: conditional amplitudes/phases remain jointly dependent, amplitudes are not bounded by 1, this does not turn an arbitrary-rank Gaussian model into a two-factor model, and an ordinary dimension-dependent perimeter/max bound does not prove the desired dimension-free scale. Any half-coefficient or common rank-mass inequality is entirely unproved. This changes neither Sigma nor the original Gaussian law, unlike covariance-completion interpolation, but without a verifiable paired-rank charge it is only a speculative direction.

---
type: idea
title: 高斯噪声与表面积工具的适用方向及未支付项
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - literature
  - gaussian-noise
  - replica-splitting
---

Primary source scoped read: Pravesh Kothari, Amir Nayyeri, Ryan O'Donnell, Chenggang Wu, Testing Surface Area, author manuscript dated August 27, 2013, https://www.cs.cmu.edu/~odonnell/papers/testing-surface-area.pdf. Section 5 defines Gaussian angular noise by cos(delta)x+sin(delta)z. Theorem5.5 bounds indicator noise sensitivity from above by sqrt(2/pi) times delta times Gaussian surface area, with attribution to Ledoux1994/Pisier. Proposition5.8 and its proof give sqrt(2/pi)cot(delta) Lipschitz smoothing for bounded functions in [-1,1]. These facts were checked in the author PDF; no claim of complete-paper verification or new library dependency is made.

Possible use: a nonlocal Gaussian noise quantity can retain continuous FDP variation in a smooth large-N limit where the microscopic squared BH face-jump energy tends to zero (see idea_4e81c20a9923). However, this cited direction of inequality is noise<=perimeter; it does not prove a bound on the FDP mean or the missing signed flux. Global model extremality bounds a perturbed FDR expectation, which is signed, and cannot automatically be replaced by the positive mean-square FDP difference. Splitting exact coordinate clones with independent private Gaussian noise is a concrete admissible model variation currently under audit. It must retain actual largest rank, labels, and denominator and must produce a new nonlocal estimate beyond existing covariance/anchor variations before being turned into a plan. If the source tool carries a step, reprove it inline or import/verify it through the native source workflow first; no silent dependency is permitted.

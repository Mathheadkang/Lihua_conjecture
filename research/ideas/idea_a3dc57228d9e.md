---
type: idea
title: Replace pointwise Stein transmission by exact Gaussian face integrals
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags:
  - integrated-transmission
  - finite-lp
  - gaussian-faces
---

New certificate proposal, NOT a proved bound. Retain the fixed cellwise vector field(A), α_C∈R^N and β_Ci∈[0,1], and pointwise rectangular box budget(C) of the failed CS64 plan. Replace each face's pointwise transmission inequality(T) by its actual Gaussian surface integral ≥0: ∫_F <n_F,A_plus−A_minus>φ_d dH≥0, with n oriented increasing observation coordinate. For each fixed finite PD model there are finitely many grid cells/faces; all truncated conditional Gaussian moments and cell endpoint coefficients are explicit model inputs, so this is a finite linear feasibility system after standard support-function linearization. Per-face integral positivity is still stronger than aggregate expectation and the ansatz is restricted, so this is not merely setting unknown meanFDR as a coefficient. Crucially, no bound may replace a surface integral by its worst point or erase its actual covariance/means. Start at ALL faces/cells of the failed N2 θ=(0,1),ρ=−.9 family, including unbounded intervals and q→0; satisfying its two former key faces alone is insufficient. Independent planner computed that one formerly impossible middle-face β capacity becomes a truncated weighted average <1 asymptotically, so the prior pointwise obstruction does not immediately transfer. Core unproved obligation: construct uniform D=64log(2+u) feasible coefficients through an actual finite-LP separation dual and a new Gaussian truncated-moment/rank identity. Must reject on a certified low-dimensional dual obstruction rather than silently enlarge constant/basis. Singular PSD passage only after a uniform finite bound. This is a possible new route and may fail.

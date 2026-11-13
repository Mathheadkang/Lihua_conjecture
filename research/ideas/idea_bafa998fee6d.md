---
type: idea
title: Monte Carlo search finds no Gaussian family with Simes size above about 1.002q
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_simes_one_sided_uniform_linear_bound
tags:
  - global-null-simes
  - numerics
---

Agent numerical experiment, 12 November 2026; scratchpad only, not a project result. Serves [the global-null Simes question](idea_b897932e6b15.md).

About 600 configurations: simplices and simplex blocks, antithetic pairs and mixtures, random signed sphere frames (dimension 2 to 100, loading 0.5 to 1), sign-cube frames, mixed-sign one-factor models, and an adversarial search over loading matrices (factor dimension up to 5, $N$ 200 to 2000, common random numbers, fresh-sample re-estimation). Levels $q\in\{0.05,0.01,10^{-3},10^{-4}\}$ (smaller only for tiny $N$); $N$ up to $10^4$ at $q\ge0.01$.

Findings: every reading above 1 fell back to 1 within error on fresh samples (largest raw 1.113 plus or minus 0.053; rerun 1.002 plus or minus 0.016). Exact integration gives the only confirmed excesses: $1.0004q$ for the 3-simplex and $1.0018q$ for the best 3-vector frame in the plane at $q=0.05$, both $1.0000q$ by $q=10^{-3}$. With residual noise the ratio rises toward 1 from below as $q$ falls; it never grows past 1. Limits: Gaussian factor models only, no importance sampling, high-rank structures only as random frames, exact integration unreliable at rank above about 100. Evidence that $C$ in the linear bound may be close to 1, not a proof.

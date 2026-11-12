---
type: idea
title: Weak global spectral residuals can retain the leading Gaussian BH inflation
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags:
  - spectral-truncation
  - rare-ranks
  - lower-bound-obstruction
---

Source-based obstruction independently cold-checked against approved lei2026_one_sided_fdr_lower and its original pp43–45,57–58. For every fixed q∈(0,1),δ>0,ε∈(0,1), there is a finite positive-definite one-factor model with null means0, alternative means>0, FDR≥(1−ε)ℓ_≤(q), yet ||Σ||op/N≤δ and average squared off-diagonal correlations arbitrarily small. The source has null loading r and mass1−r−τ, alternative loading−1 and mass r+τ, τ~(1−q)r²/q. Its squared-loading budget→0 as r→0. Take source expectation over random iid types (not a pointwise finite-sample source bound), then choose a deterministic realization simultaneously high-FDR and low-loading via boundedness and Hoeffding, followed by finite-N positive-definite perturbation. Thus total-N-normalized weak dependence cannot approximate BH by independence even at fixedq; rare rejection fractions are the obstacle. Stronger padding construction: clone the source block d times and add d independent huge-negative-mean null clone blocks filling half the total tests. They occupy the entire top-d spectral eigenspace while the source dependence remains in a residual with arbitrarily small ||S||op/N. Full BH on the active block has effective levelq/2 outside a tiny padding-rejection event. Diagonalizing the residual preserves means/variances but loses FDR at least ℓ_≤(q/2)−q/2−3h, giving a leading-scale lower bound of q sqrt(log(1/q))/(2sqrtπ) when h=o(qsqrtlog). This is a lower bound on the difference, not a proved asymptotic equality. The padding model may be singular, which is admissible. Valid Hermite fixed-threshold variance inequality Var(N^-1Σf_i(Gi))≤||R||op N^-2ΣVar(f_i) does not yield relative control at BH-selected rare ranks. Source/proof note research-local/gaussian_weak_spectral_fdr_obstruction_20261104T202938Z.md; independent review research-local/gaussian_weak_spectral_fdr_cold_review_20261104_v1.md. Neither statement refutes the original sharp upper conjecture; future spectral routes require rank-local information or direct residual control.

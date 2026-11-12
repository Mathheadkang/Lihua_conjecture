---
type: search_round
title: Baseline-subtracted pivotal core round 1 structural obstructions
target_asset: gaussian_bh_baseline_subtracted_pivotal_core
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates: []
statement_digest: 182210875024e41e07afd86320271d77d4c3101bb674953cf99e16eee40678ba
performed_by: unknown
created_at: '2026-11-06T20:52:57.891Z'
extension_version: 0.0.4
---

## Obstructions

- A failure based only on singular covariance destroying frozen-threshold independence is obstructed by joint Gaussian independence: each retained nonmover has zero covariance with the null coordinate, so their joint vector is independent of that coordinate even when its covariance matrix is singular. The mover coordinates in the frozen vector are constants. Thus the frozen threshold is independent of the null p-value. Its values lie in $[q/N,q]$, and conditional uniformity gives $\mathbb E[a(T_i;\tau_i^\flat)]=1$. This is a proof-route observation to be checked in formal proof execution, not a verified proof verdict.
- A failure based on the sign of the subtracted expression is obstructed by coordinate monotonicity of the BH step-up count. Replacing mover p-values by one can only decrease the count, hence $0<\tau_i^\flat\le\tau_i$. For $p\le\tau_i^\flat$, the difference is $1/\tau_i-1/\tau_i^\flat\le0$; for $\tau_i^\flat<p\le\tau_i$, it equals $1/\tau_i$; and for $p>\tau_i$, it is zero. These regimes support the proposed pointwise upper inequality, subject to formal proof execution.
- An empty mover set cannot supply a counterexample through baseline subtraction: then the two threshold vectors coincide. In particular, $N=1$ gives both thresholds equal to $q$ and the uniform null p-value gives $\Delta_i=0$.
- Letting the finite dimension depend arbitrarily on $q$ does not evade these structural observations: the independence argument, positive lower threshold $q/N$, and three pointwise regimes apply separately at every finite admissible $(N,q)$. No uniform-in-dimension asymptotic approximation was used in these observations.

## Limitations

- All five round-1 workers reported no admissible counterexample and wrote no candidate files. There is consequently no independently verified survivor or candidate-level failure ledger from this round.
- This record consolidates the reported structural observations; it is not an exhaustive search over means, covariance matrices, dimensions, or levels, and it reports no numerical experiment or computational certification.
- Formal proof execution and independent proof verification remain outstanding. In particular, the Gaussian independence and BH monotonicity arguments must be written and checked against the target's exact definitions rather than promoted to approval by this search summary.
- No stronger bound for the positive crossing term, no unrestricted Gaussian BH conjecture, and no claim beyond this pivotal-core statement were established in this round.
